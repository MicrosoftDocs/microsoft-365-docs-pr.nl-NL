---
title: Referentie voor gegevensverliespreventie
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: referentiemateriaal ter voorkoming van gegevensverlies
ms.openlocfilehash: a6dc0b2702899e05f78c54331fb33b87495672d8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572559"
---
# <a name="data-loss-prevention-reference"></a><span data-ttu-id="5cf30-103">Referentie voor preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="5cf30-103">Data loss prevention reference</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="5cf30-104">Dit is referentieonderwerp is niet langer de belangrijkste bron voor Microsoft 365 DLP-informatie (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="5cf30-104">This is reference topic is no longer the main resource for Microsoft 365 data loss prevention (DLP) information.</span></span> <span data-ttu-id="5cf30-105">De DLP-inhoudsset wordt bijgewerkt en geherstructureerd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-105">The DLP content set is being updated and restructured.</span></span> <span data-ttu-id="5cf30-106">De onderwerpen die in dit artikel worden behandeld, worden verplaatst naar nieuwe, bijgewerkte artikelen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-106">The topics covered in this article will be moving to new, updated articles.</span></span> <span data-ttu-id="5cf30-107">Zie Meer informatie over [preventie van gegevensverlies voor](dlp-learn-about-dlp.md)meer informatie over DLP.</span><span class="sxs-lookup"><span data-stu-id="5cf30-107">For more information about DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> <span data-ttu-id="5cf30-108">Mogelijkheden voor het voorkomen van gegevensverlies zijn onlangs toegevoegd aan Microsoft Teams chat- en kanaalberichten voor gebruikers die een licentie hebben voor Office 365 Advanced Compliance, die beschikbaar is als een zelfstandige optie en is opgenomen in Office 365 E5- en Microsoft 365 E5 Compliance.</span><span class="sxs-lookup"><span data-stu-id="5cf30-108">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="5cf30-109">Zie [Microsoft 365 Tenant-Level Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)voor services voor meer informatie over licentievereisten.</span><span class="sxs-lookup"><span data-stu-id="5cf30-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a><span data-ttu-id="5cf30-110">DLP-beleid maken en beheren</span><span class="sxs-lookup"><span data-stu-id="5cf30-110">Create and manage DLP policies</span></span>

<span data-ttu-id="5cf30-111">U maakt en beheert DLP-beleid op de pagina Preventie van gegevensverlies in het Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="5cf30-111">You create and manage DLP policies on the Data loss prevention page in the Microsoft 365 Compliance center.</span></span>
  
![Pagina preventie gegevensverlies in het Office 365 Security &amp; Compliance Center](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
<span data-ttu-id="5cf30-113">U kunt een regel gebruiken om aan een specifieke beveiligings vereiste te voldoen en vervolgens een DLP-beleid gebruiken om gemeenschappelijke beveiligings vereisten te groeperen, zoals alle regels die nodig zijn om aan een specifieke verordening te voldoen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-113">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="5cf30-114">U hebt bijvoorbeeld een DLP-beleid waarmee u de aanwezigheid van informatie kunt detecteren die onder de Health Insurance Portability and Accountability Act (HIPAA) vallen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-114">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="5cf30-115">Dit DLP-beleid kan helpen bij het beschermen van HIPAA-gegevens (de wat) op alle SharePoint online sites en alle OneDrive voor Bedrijven sites (de waar) door een document te vinden dat deze gevoelige informatie bevat die wordt gedeeld met mensen buiten uw organisatie (de voorwaarden) en vervolgens de toegang tot het document te blokkeren en een melding (de acties) te verzenden.</span><span class="sxs-lookup"><span data-stu-id="5cf30-115">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="5cf30-116">Deze vereisten worden opgeslagen als afzonderlijke regels en gegroepeerd als een DLP-beleid om het beheer en de rapportage te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-116">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![Diagram laat zien dat DLP-beleid locaties en regels bevat](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

<span data-ttu-id="5cf30-118">Als u ervoor kiest om specifieke distributiegroepen op te nemen in Exchange, wordt het DLP-beleid alleen beperkt tot de leden van die groep.</span><span class="sxs-lookup"><span data-stu-id="5cf30-118">If you choose to include specific distribution groups in Exchange, the DLP policy will be scoped only to the members of that group.</span></span> <span data-ttu-id="5cf30-119">Als u een distributiegroep uitsluit, worden alle leden van die distributiegroep uitgesloten van beleidsevaluatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-119">Similarly excluding a distribution group will exclude all the members of that distribution group from policy evaluation.</span></span> <span data-ttu-id="5cf30-120">U kunt ervoor kiezen om een beleid te beperken tot de leden van distributielijsten, dynamische distributiegroepen en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-120">You can choose to scope a policy to the members of distribution lists, dynamic distribution groups, and security groups.</span></span> <span data-ttu-id="5cf30-121">Een DLP-beleid mag niet meer dan 50 van dergelijke insluitsels en uitsluitingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="5cf30-121">A DLP policy can contain no more than 50 such inclusions and exclusions.</span></span>

<span data-ttu-id="5cf30-122">Als u ervoor kiest om specifieke SharePoint sites op te nemen of uit te sluiten, mag een DLP-beleid niet meer dan 100 van dergelijke insluitsels en uitsluitingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="5cf30-122">If you choose to include or exclude specific SharePoint sites, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="5cf30-123">Hoewel deze limiet bestaat, kunt u deze limiet overschrijden door een organisatiebreed beleid of een beleid toe te passen dat van toepassing is op hele locaties.</span><span class="sxs-lookup"><span data-stu-id="5cf30-123">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>

<span data-ttu-id="5cf30-124">Als u ervoor kiest om specifieke OneDrive accounts of groepen op te nemen of uit te sluiten, mag een DLP-beleid niet meer dan 100 gebruikersaccounts of 50 groepen bevatten als opname of uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="5cf30-124">If you choose to include or exclude specific OneDrive accounts or groups, a DLP policy can contain no more than 100 user accounts or 50 groups as inclusion or exclusion.</span></span>

> [!NOTE]
> <span data-ttu-id="5cf30-125">OneDrive voor het zoeken naar bedrijfsbeleid met behulp van accounts of groepen is in de openbare preview-versie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-125">OneDrive for business policy scoping using accounts or groups is in public preview.</span></span> <span data-ttu-id="5cf30-126">Tijdens deze fase kunt u gebruikersaccounts en groepen opnemen of uitsluiten als onderdeel van een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-126">During this phase, you can either include or exclude user accounts and groups as part of a DLP policy.</span></span> <span data-ttu-id="5cf30-127">Zowel inclusie als uitsluiting als onderdeel van hetzelfde beleid wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="5cf30-127">Both inclusion and exclusion as part of the same policy is not supported.</span></span>
  
### <a name="rules"></a><span data-ttu-id="5cf30-128">Regels</span><span class="sxs-lookup"><span data-stu-id="5cf30-128">Rules</span></span>

> [!NOTE]
> <span data-ttu-id="5cf30-129">Het standaardgedrag van een DLP-beleid, wanneer er geen waarschuwing is geconfigureerd, is niet te waarschuwen of te activeren.</span><span class="sxs-lookup"><span data-stu-id="5cf30-129">The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger.</span></span> <span data-ttu-id="5cf30-130">Dit geldt alleen voor standaardinformatietypen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-130">This applies only to default information types.</span></span> <span data-ttu-id="5cf30-131">Voor aangepaste informatietypen wordt het systeem gewaarschuwd, zelfs als er geen actie is gedefinieerd in het beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-131">For custom information types, the system will alert even if there is no action defined in the policy.</span></span>

<span data-ttu-id="5cf30-132">Regels zijn de vereisten van uw bedrijf op de inhoud van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-132">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="5cf30-133">Een beleid bevat een of meer regels en elke regel bestaat uit voorwaarden en acties.</span><span class="sxs-lookup"><span data-stu-id="5cf30-133">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="5cf30-134">Voor elke regel, wanneer aan de voorwaarden is voldaan, worden de acties automatisch uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-134">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="5cf30-135">Regels worden opeenvolgend uitgevoerd, te beginnen met de regel met de hoogste prioriteit in elk beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-135">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="5cf30-136">Een regel biedt ook opties om gebruikers (met beleidstips en e-mailmeldingen) en beheerders (met e-mailincidentrapporten) te informeren dat de inhoud overeenkomt met de regel.</span><span class="sxs-lookup"><span data-stu-id="5cf30-136">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="5cf30-137">Hier zijn de componenten van een regel, elk hieronder uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-137">Here are the components of a rule, each explained below.</span></span>
  
![Secties van de DLP-regeleditor](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="5cf30-139">Voorwaarden</span><span class="sxs-lookup"><span data-stu-id="5cf30-139">Conditions</span></span>

<span data-ttu-id="5cf30-140">Voorwaarden zijn belangrijk omdat ze bepalen welke soorten informatie u zoekt en wanneer u actie moet ondernemen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-140">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="5cf30-141">U kunt er bijvoorbeeld voor kiezen om inhoud met paspoortnummers te negeren, tenzij de inhoud meer dan 10 van dergelijke nummers bevat en wordt gedeeld met mensen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-141">For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="5cf30-142">Voorwaarden zijn gericht op de **inhoud,** zoals welke typen gevoelige informatie u zoekt, en ook op de **context,** zoals met wie het document wordt gedeeld.</span><span class="sxs-lookup"><span data-stu-id="5cf30-142">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="5cf30-143">U kunt voorwaarden gebruiken om verschillende acties toe te wijzen aan verschillende risiconiveaus.</span><span class="sxs-lookup"><span data-stu-id="5cf30-143">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="5cf30-144">Gevoelige inhoud die intern wordt gedeeld, kan bijvoorbeeld een lager risico vormen en vereist minder acties dan gevoelige inhoud die wordt gedeeld met mensen buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-144">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![Lijst met beschikbare DLP-voorwaarden](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="5cf30-146">De voorwaarden die nu beschikbaar zijn, kunnen bepalen of:</span><span class="sxs-lookup"><span data-stu-id="5cf30-146">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="5cf30-147">Inhoud bevat een type gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-147">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="5cf30-148">Inhoud bevat een label.</span><span class="sxs-lookup"><span data-stu-id="5cf30-148">Content contains a label.</span></span> <span data-ttu-id="5cf30-149">Zie de onderstaande sectie [Een bewaarlabel gebruiken als voorwaarde in een DLP-beleid](#using-a-retention-label-as-a-condition-in-a-dlp-policy)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-149">For more information, see the below section [Using a retention label as a condition in a DLP policy](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="5cf30-150">Inhoud wordt gedeeld met mensen buiten of binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-150">Content is shared with people outside or inside your organization.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5cf30-151">Gebruikers die niet-gastaccounts hebben in active directory of Azure Active Directory tenant van een hostorganisatie, worden beschouwd als personen binnen de organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-151">Users who have non-guest accounts in a host organization's Active Directory or Azure Active Directory tenant are considered as people inside the organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="5cf30-152">Soorten gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="5cf30-152">Types of sensitive information</span></span>

<span data-ttu-id="5cf30-153">Met een DLP-beleid wordt gevoelige informatie beschermd, die is gedefinieerd als een **type gevoelige informatie**.</span><span class="sxs-lookup"><span data-stu-id="5cf30-153">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="5cf30-154">Microsoft 365 bevat definities voor veel veelvoorkomende typen gevoelige informatie in veel verschillende regio's die klaar zijn voor gebruik, zoals een creditcardnummer, bankrekeningnummers, nationale ID-nummers en paspoortnummers.</span><span class="sxs-lookup"><span data-stu-id="5cf30-154">Microsoft 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![Lijst met beschikbare typen gevoelige informatie](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="5cf30-156">Wanneer een DLP-beleid zoekt naar een gevoelig informatietype, zoals een creditcardnummer, wordt niet alleen gezocht naar een 16-cijferig nummer.</span><span class="sxs-lookup"><span data-stu-id="5cf30-156">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="5cf30-157">Elk gevoelig informatietype wordt gedefinieerd en gedetecteerd met behulp van een combinatie van:</span><span class="sxs-lookup"><span data-stu-id="5cf30-157">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="5cf30-158">Zoekwoorden.</span><span class="sxs-lookup"><span data-stu-id="5cf30-158">Keywords.</span></span>
    
- <span data-ttu-id="5cf30-159">Interne functies om controlesommen of samenstelling te valideren.</span><span class="sxs-lookup"><span data-stu-id="5cf30-159">Internal functions to validate checksums or composition.</span></span>
    
- <span data-ttu-id="5cf30-160">Evaluatie van reguliere expressies om patroonmatches te vinden.</span><span class="sxs-lookup"><span data-stu-id="5cf30-160">Evaluation of regular expressions to find pattern matches.</span></span>
    
- <span data-ttu-id="5cf30-161">Ander inhoudsonderzoek.</span><span class="sxs-lookup"><span data-stu-id="5cf30-161">Other content examination.</span></span>
    
<span data-ttu-id="5cf30-162">Dit helpt DLP-detectie een hoge mate van nauwkeurigheid te bereiken en tegelijkertijd het aantal valse positieven te verminderen dat het werk van mensen kan onderbreken.</span><span class="sxs-lookup"><span data-stu-id="5cf30-162">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="5cf30-163">Acties</span><span class="sxs-lookup"><span data-stu-id="5cf30-163">Actions</span></span>

<span data-ttu-id="5cf30-164">Wanneer inhoud overeenkomt met een voorwaarde in een regel, kunt u acties toepassen om de inhoud automatisch te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-164">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![Lijst met beschikbare DLP-acties](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="5cf30-166">Met de acties die nu beschikbaar zijn, kunt u:</span><span class="sxs-lookup"><span data-stu-id="5cf30-166">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="5cf30-167">**De toegang tot de inhoud beperken** Afhankelijk van uw behoefte kunt u de toegang tot inhoud op drie manieren beperken:</span><span class="sxs-lookup"><span data-stu-id="5cf30-167">**Restrict access to the content** Depending on your need, you can restrict access to content in three ways:</span></span>

  1. <span data-ttu-id="5cf30-168">Beperk de toegang tot inhoud voor iedereen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-168">Restrict access to content for everyone.</span></span>
  2. <span data-ttu-id="5cf30-169">Beperk de toegang tot inhoud voor mensen buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-169">Restrict access to content for people outside the organization.</span></span>
  3. <span data-ttu-id="5cf30-170">Beperk de toegang tot 'Iedereen met de link'.</span><span class="sxs-lookup"><span data-stu-id="5cf30-170">Restrict access to "Anyone with the link."</span></span>

  <span data-ttu-id="5cf30-171">Voor site-inhoud betekent dit dat machtigingen voor het document beperkt zijn voor iedereen, behalve de beheerder van de primaire siteverzameling, de eigenaar van het document en de persoon die het document voor het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-171">For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="5cf30-172">Deze personen kunnen de gevoelige informatie uit het document verwijderen of andere corrigerende maatregelen nemen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-172">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="5cf30-173">Wanneer het document voldoet, worden de oorspronkelijke machtigingen automatisch hersteld.</span><span class="sxs-lookup"><span data-stu-id="5cf30-173">When the document is in compliance, the original permissions are automatically restored.</span></span> <span data-ttu-id="5cf30-174">Wanneer de toegang tot een document wordt geblokkeerd, wordt het document weergegeven met een speciaal beleidstippictogram in de bibliotheek op de site.</span><span class="sxs-lookup"><span data-stu-id="5cf30-174">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
  ![Beleidstip met toegang tot document is geblokkeerd](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  <span data-ttu-id="5cf30-176">Voor e-mailinhoud blokkeert deze actie dat het bericht wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="5cf30-176">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="5cf30-177">Afhankelijk van hoe de DLP-regel is geconfigureerd, ziet de afzender een NDR of (als de regel een melding gebruikt) een beleidstip en/of e-mailmelding.</span><span class="sxs-lookup"><span data-stu-id="5cf30-177">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
  ![Waarschuwing dat onbevoegde geadresseerden uit het bericht moeten worden verwijderd](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="5cf30-179">Gebruikersmeldingen en gebruikersoverschrijvingen</span><span class="sxs-lookup"><span data-stu-id="5cf30-179">User notifications and user overrides</span></span>

<span data-ttu-id="5cf30-180">U kunt meldingen en overschrijvingen gebruiken om uw gebruikers te informeren over DLP-beleid en hen te helpen compliant te blijven zonder hun werk te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="5cf30-180">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="5cf30-181">Als een gebruiker bijvoorbeeld probeert een document met gevoelige informatie te delen, kan een DLP-beleid hen zowel een e-mailmelding sturen als een beleidstip weergeven in de context van de documentbibliotheek waarmee ze het beleid kunnen overschrijven als ze een zakelijke rechtvaardiging hebben.</span><span class="sxs-lookup"><span data-stu-id="5cf30-181">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![Gebruikersmeldingen en gebruikersoverschrijvingen secties van DLP-regeleditor](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="5cf30-183">De e-mail kan de persoon op de hoogte stellen die de inhoud heeft verzonden, gedeeld of voor het laatst heeft gewijzigd en, voor site-inhoud, de beheerder en documenteigenaar van de primaire siteverzameling.</span><span class="sxs-lookup"><span data-stu-id="5cf30-183">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="5cf30-184">Bovendien kunt u toevoegen of verwijderen wie u maar wilt uit de e-mailmelding.</span><span class="sxs-lookup"><span data-stu-id="5cf30-184">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="5cf30-185">Naast het verzenden van een e-mailmelding, wordt in een gebruikersmelding een beleidstip weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5cf30-185">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="5cf30-186">In Outlook en Outlook op het web.</span><span class="sxs-lookup"><span data-stu-id="5cf30-186">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="5cf30-187">Voor het document op een SharePoint Online of OneDrive voor Bedrijven site.</span><span class="sxs-lookup"><span data-stu-id="5cf30-187">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="5cf30-188">In Excel, PowerPoint en Word wanneer het document wordt opgeslagen op een site die is opgenomen in een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-188">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="5cf30-189">In de e-mailmelding en beleidstip wordt uitgelegd waarom inhoud conflicteert met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-189">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="5cf30-190">Als u dit wilt, kunnen gebruikers met de e-mailmelding en beleidstip een regel overschrijven door een vals positief te melden of een zakelijke rechtvaardiging te geven.</span><span class="sxs-lookup"><span data-stu-id="5cf30-190">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="5cf30-191">Dit kan u helpen gebruikers te informeren over uw DLP-beleid en ze af te dwingen zonder te voorkomen dat mensen hun werk doen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-191">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="5cf30-192">Informatie over overschrijvingen en valse positieven wordt ook geregistreerd voor rapportage (zie hieronder over de DLP-rapporten) en opgenomen in de incidentrapporten (volgende sectie), zodat de compliance officer deze informatie regelmatig kan controleren.</span><span class="sxs-lookup"><span data-stu-id="5cf30-192">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="5cf30-193">Zo ziet een beleidstip eruit in een OneDrive voor Bedrijven account.</span><span class="sxs-lookup"><span data-stu-id="5cf30-193">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![Beleidstip voor een document in een OneDrive account](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 <span data-ttu-id="5cf30-195">Zie Meldingen en beleidstips gebruiken voor meer informatie over [gebruikersmeldingen en beleidstips in DLP-beleid.](use-notifications-and-policy-tips.md)</span><span class="sxs-lookup"><span data-stu-id="5cf30-195">To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).</span></span>

#### <a name="alerts-and-incident-reports"></a><span data-ttu-id="5cf30-196">Meldingen en incidentrapporten</span><span class="sxs-lookup"><span data-stu-id="5cf30-196">Alerts and Incident reports</span></span>

<span data-ttu-id="5cf30-197">Wanneer een regel is afgestemd, kunt u een waarschuwingsmail sturen naar uw compliance officer (of een persoon(en) die u kiest) met details van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="5cf30-197">When a rule is matched, you can send an alert email to your compliance officer ( or any person(s) you choose) with details of the alert.</span></span> <span data-ttu-id="5cf30-198">Deze waarschuwingsmail bevat een koppeling van het [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) waarmee de compliance officer de details van waarschuwingen en gebeurtenissen kan bekijken.</span><span class="sxs-lookup"><span data-stu-id="5cf30-198">This alert email will carry a link of the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) which the compliance officer can go to view the details of alert and events.</span></span> <span data-ttu-id="5cf30-199">Het dashboard bevat details van de gebeurtenis die de waarschuwing heeft geactiveerd, samen met details van het DLP-beleid dat overeenkomt en de gedetecteerde gevoelige inhoud.</span><span class="sxs-lookup"><span data-stu-id="5cf30-199">The dashboard contains details of the event that triggered the alert along with details of the DLP policy matched and the sensitive content detected.</span></span>

<span data-ttu-id="5cf30-200">Daarnaast kunt u ook een incidentmelding sturen met details van de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="5cf30-200">In addition, you can also send an incident report with details of the event.</span></span> <span data-ttu-id="5cf30-201">Dit rapport bevat informatie over het item dat is overeenkomend, de werkelijke inhoud die overeenkomt met de regel en de naam van de persoon die de inhoud voor het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-201">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="5cf30-202">Voor e-mailberichten bevat het rapport ook als bijlage het oorspronkelijke bericht dat overeenkomt met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-202">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5cf30-203">![Pagina voor het configureren van incidentrapporten](../media/Alerts-and-incident-report.png)</span><span class="sxs-lookup"><span data-stu-id="5cf30-203">![Page for configuring incident reports](../media/Alerts-and-incident-report.png)</span></span>

<span data-ttu-id="5cf30-204">DLP scant e-mail anders dan items in SharePoint Online of OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="5cf30-204">DLP scans email differently from items in SharePoint Online or OneDrive for Business.</span></span> <span data-ttu-id="5cf30-205">In SharePoint Online en OneDrive voor Bedrijven scant DLP zowel bestaande als nieuwe items en genereert een waarschuwings- en incidentrapport wanneer een overeenkomst wordt gevonden.</span><span class="sxs-lookup"><span data-stu-id="5cf30-205">In SharePoint Online and OneDrive for Business, DLP scans existing items as well as new ones and generates an alert and incident report whenever a match is found.</span></span> <span data-ttu-id="5cf30-206">In Exchange Online scant DLP alleen nieuwe e-mailberichten en genereert een rapport als er een beleids overeenkomst is.</span><span class="sxs-lookup"><span data-stu-id="5cf30-206">In Exchange Online, DLP only scans new email messages and generates a report if there is a policy match.</span></span> <span data-ttu-id="5cf30-207">DLP ***scant*** of komt niet overeen met eerder bestaande e-mailitems die zijn opgeslagen in een postvak of archief.</span><span class="sxs-lookup"><span data-stu-id="5cf30-207">DLP ***does not*** scan or match previously existing email items that are stored in a mailbox or archive.</span></span>
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="5cf30-208">Groepering en logische operatoren</span><span class="sxs-lookup"><span data-stu-id="5cf30-208">Grouping and logical operators</span></span>

<span data-ttu-id="5cf30-209">Vaak heeft uw DLP-beleid een eenvoudige vereiste, zoals het identificeren van alle inhoud die een Amerikaans burgerservicenummer bevat.</span><span class="sxs-lookup"><span data-stu-id="5cf30-209">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="5cf30-210">In andere scenario's moet uw DLP-beleid echter mogelijk meer los gedefinieerde gegevens identificeren.</span><span class="sxs-lookup"><span data-stu-id="5cf30-210">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="5cf30-211">Als u bijvoorbeeld inhoud wilt identificeren die onder de Amerikaanse Health Insurance Act (HIPAA) vallen, moet u zoeken naar:</span><span class="sxs-lookup"><span data-stu-id="5cf30-211">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="5cf30-212">Inhoud die specifieke soorten gevoelige informatie bevat, zoals een Amerikaans burgerservicenummer of een DEA-nummer (Drug Enforcement Agency).</span><span class="sxs-lookup"><span data-stu-id="5cf30-212">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="5cf30-213">en</span><span class="sxs-lookup"><span data-stu-id="5cf30-213">AND</span></span>
    
- <span data-ttu-id="5cf30-214">Inhoud die moeilijker te identificeren is, zoals communicatie over de zorg van een patiënt of beschrijvingen van medische diensten die worden aangeboden.</span><span class="sxs-lookup"><span data-stu-id="5cf30-214">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="5cf30-215">Om deze inhoud te identificeren, moeten trefwoorden uit zeer grote trefwoordenlijsten worden gematcht, zoals de International Classification of Diseases (ICD-9-CM of ICD-10-CM).</span><span class="sxs-lookup"><span data-stu-id="5cf30-215">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="5cf30-216">U kunt dergelijke los gedefinieerde gegevens eenvoudig identificeren met behulp van groeperings- en logische operatoren (AND, OR).</span><span class="sxs-lookup"><span data-stu-id="5cf30-216">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="5cf30-217">Wanneer u een DLP-beleid maakt, kunt u het aantal:</span><span class="sxs-lookup"><span data-stu-id="5cf30-217">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="5cf30-218">Typen gevoelige informatie groeperen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-218">Group sensitive information types.</span></span>
    
- <span data-ttu-id="5cf30-219">Kies de logische operator tussen de gevoelige informatietypen binnen een groep en tussen de groepen zelf.</span><span class="sxs-lookup"><span data-stu-id="5cf30-219">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="5cf30-220">De operator binnen een groep kiezen</span><span class="sxs-lookup"><span data-stu-id="5cf30-220">Choosing the operator within a group</span></span>

<span data-ttu-id="5cf30-221">Binnen een groep kunt u kiezen of aan een of alle voorwaarden in die groep moet worden voldaan om de inhoud aan de regel te laten voldoen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-221">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![Groep met de operatoren binnen de groep](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="5cf30-223">Een groep toevoegen</span><span class="sxs-lookup"><span data-stu-id="5cf30-223">Adding a group</span></span>

<span data-ttu-id="5cf30-224">U kunt snel een groep toevoegen, die zijn eigen voorwaarden en operator binnen die groep kan hebben.</span><span class="sxs-lookup"><span data-stu-id="5cf30-224">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![Knop Groep toevoegen](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="5cf30-226">De operator kiezen tussen groepen</span><span class="sxs-lookup"><span data-stu-id="5cf30-226">Choosing the operator between groups</span></span>

<span data-ttu-id="5cf30-227">Tussen groepen kunt u kiezen of aan de voorwaarden in slechts één groep of aan alle groepen moet worden voldaan om de inhoud aan de regel te laten voldoen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-227">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="5cf30-228">Het ingebouwde **AMERIKAANSE HIPAA-beleid** heeft bijvoorbeeld een regel die een **AND-operator** tussen de groepen gebruikt, zodat deze inhoud identificeert die het volgende bevat:</span><span class="sxs-lookup"><span data-stu-id="5cf30-228">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="5cf30-229">van de **pii-id's** van de groep (ten minste één SSN-nummer **of** DEA-nummer)</span><span class="sxs-lookup"><span data-stu-id="5cf30-229">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="5cf30-230">**en**</span><span class="sxs-lookup"><span data-stu-id="5cf30-230">**AND**</span></span>
    
- <span data-ttu-id="5cf30-231">uit de groep **Medische Termen** (ten minste één ICD-9-CM trefwoord **OF** ICD-10-CM trefwoord)</span><span class="sxs-lookup"><span data-stu-id="5cf30-231">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![Groepen die de operator tussen groepen weergeven](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="5cf30-233">De prioriteit waarmee regels worden verwerkt</span><span class="sxs-lookup"><span data-stu-id="5cf30-233">The priority by which rules are processed</span></span>

<span data-ttu-id="5cf30-234">Wanneer u regels in een beleid maakt, krijgt aan elke regel een prioriteit toegewezen in de volgorde waarin deze is gemaakt, wat betekent dat de regel die als eerste is gemaakt, de eerste prioriteit heeft, de regel die als tweede is gemaakt, de tweede prioriteit, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="5cf30-234">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5cf30-235">![Regels in prioriteitsvolgorde](../media/dlp-rules-in-priority-order.png)</span><span class="sxs-lookup"><span data-stu-id="5cf30-235">![Rules in priority order](../media/dlp-rules-in-priority-order.png)</span></span>
  
<span data-ttu-id="5cf30-236">Nadat u meer dan één DLP-beleid hebt ingesteld, kunt u de prioriteit van een of meer beleidsregels wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-236">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="5cf30-237">Selecteer hiervoor een beleid, kies **Beleid bewerken** en gebruik de lijst **Prioriteit** om de prioriteit op te geven.</span><span class="sxs-lookup"><span data-stu-id="5cf30-237">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5cf30-238">![Prioriteit instellen voor een beleid](../media/dlp-set-policy-priority.png)</span><span class="sxs-lookup"><span data-stu-id="5cf30-238">![Set priority for a policy](../media/dlp-set-policy-priority.png)</span></span>

<span data-ttu-id="5cf30-239">Wanneer inhoud wordt geëvalueerd aan de hand van regels, worden de regels in prioriteitsvolgorde verwerkt.</span><span class="sxs-lookup"><span data-stu-id="5cf30-239">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="5cf30-240">Als inhoud overeenkomt met meerdere regels, worden de regels in prioriteitsvolgorde verwerkt en wordt de meest beperkende actie afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-240">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="5cf30-241">Als inhoud bijvoorbeeld overeenkomt met alle volgende regels, wordt regel 3 afgedwongen omdat dit de hoogste prioriteit heeft, de meest beperkende regel:</span><span class="sxs-lookup"><span data-stu-id="5cf30-241">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="5cf30-242">Regel 1: informeert gebruikers alleen</span><span class="sxs-lookup"><span data-stu-id="5cf30-242">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="5cf30-243">Regel 2: waarschuwt gebruikers, beperkt de toegang en staat gebruikersoverschrijvingen toe</span><span class="sxs-lookup"><span data-stu-id="5cf30-243">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="5cf30-244">Regel 3: waarschuwt gebruikers, beperkt de toegang en staat gebruikersoverschrijvingen niet toe</span><span class="sxs-lookup"><span data-stu-id="5cf30-244">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="5cf30-245">Regel 4: informeert gebruikers alleen</span><span class="sxs-lookup"><span data-stu-id="5cf30-245">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="5cf30-246">Regel 5: beperkt de toegang</span><span class="sxs-lookup"><span data-stu-id="5cf30-246">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="5cf30-247">Regel 6: waarschuwt gebruikers, beperkt de toegang en staat gebruikersoverschrijvingen niet toe</span><span class="sxs-lookup"><span data-stu-id="5cf30-247">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="5cf30-248">Houd er in dit voorbeeld rekening mee dat overeenkomsten voor alle regels worden vastgelegd in de controlelogboeken en worden weergegeven in de DLP-rapporten, ook al wordt alleen de meest beperkende regel afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-248">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="5cf30-249">Wat betreft beleidstips, merk op dat:</span><span class="sxs-lookup"><span data-stu-id="5cf30-249">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="5cf30-250">Alleen de beleidstip van de hoogste prioriteit, de meest beperkende regel wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5cf30-250">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="5cf30-251">Een beleidstip van een regel die de toegang tot inhoud blokkeert, wordt bijvoorbeeld weergegeven via een beleidstip van een regel die alleen een melding verzendt.</span><span class="sxs-lookup"><span data-stu-id="5cf30-251">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="5cf30-252">Dit voorkomt dat mensen een cascade van beleidstips zien.</span><span class="sxs-lookup"><span data-stu-id="5cf30-252">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="5cf30-253">Als met de beleidstips in de meest beperkende regel mensen de regel kunnen overschrijven, worden bij het overschrijven van deze regel ook alle andere regels overschreven die overeenkomen met de inhoud.</span><span class="sxs-lookup"><span data-stu-id="5cf30-253">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="5cf30-254">Tuningregels om ze gemakkelijker of moeilijker te matchen</span><span class="sxs-lookup"><span data-stu-id="5cf30-254">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="5cf30-255">Nadat mensen hun DLP-beleid hebben gemaakt en ingeschakeld, komen ze soms deze problemen tegen:</span><span class="sxs-lookup"><span data-stu-id="5cf30-255">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="5cf30-256">Te veel inhoud die geen gevoelige informatie **is,** komt overeen met de regels, met andere woorden, te veel valse positieven.</span><span class="sxs-lookup"><span data-stu-id="5cf30-256">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="5cf30-257">Te weinig inhoud die gevoelige informatie **is,** komt overeen met de regels.</span><span class="sxs-lookup"><span data-stu-id="5cf30-257">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="5cf30-258">Met andere woorden, de beschermende acties worden niet afgedwongen op de gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-258">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="5cf30-259">Om deze problemen aan te pakken, kunt u uw regels afstemmen door het aantal exemplaren aan te passen en de nauwkeurigheid van de overeenkomst aan te passen, waardoor het voor inhoud moeilijker of gemakkelijker wordt om aan de regels te voldoen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-259">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="5cf30-260">Elk gevoelig informatietype dat in een regel wordt gebruikt, heeft zowel een aantal exemplaren als een overeenkomstnauwkeurigheid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-260">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="5cf30-261">Aantal instanties</span><span class="sxs-lookup"><span data-stu-id="5cf30-261">Instance count</span></span>

<span data-ttu-id="5cf30-262">Aantal exemplaren betekent simpelweg hoeveel exemplaren van een specifiek type gevoelige informatie aanwezig moeten zijn om inhoud aan te passen aan de regel.</span><span class="sxs-lookup"><span data-stu-id="5cf30-262">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="5cf30-263">Inhoud komt bijvoorbeeld overeen met de onderstaande regel als deze zich tussen 1 en 9 unieke Amerikaanse of Britse regels voordeed.</span><span class="sxs-lookup"><span data-stu-id="5cf30-263">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="5cf30-264">paspoortnummers worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-264">passport numbers are identified.</span></span>

> [!NOTE]
> <span data-ttu-id="5cf30-265">Het aantal exemplaren bevat alleen **unieke** overeenkomsten voor gevoelige informatietypen en trefwoorden.</span><span class="sxs-lookup"><span data-stu-id="5cf30-265">The instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="5cf30-266">Als een e-mail bijvoorbeeld 10 exemplaren van hetzelfde creditcardnummer bevat, tellen deze 10 exemplaren als één exemplaar van een creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="5cf30-266">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span>
  
<span data-ttu-id="5cf30-267">Als u het aantal exemplaren wilt gebruiken om regels af te stemmen, is de begeleiding eenvoudig:</span><span class="sxs-lookup"><span data-stu-id="5cf30-267">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="5cf30-268">Om de regel gemakkelijker te matchen, verlaagt u het **aantal minuten** en/of verhoogt u het **maximum** aantal.</span><span class="sxs-lookup"><span data-stu-id="5cf30-268">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="5cf30-269">U kunt ook **het maximum** instellen op **elke** door de numerieke waarde te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-269">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="5cf30-270">Om de regel moeilijker te matchen, verhoogt u het **aantal minuten.**</span><span class="sxs-lookup"><span data-stu-id="5cf30-270">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="5cf30-271">Meestal gebruikt u minder beperkende acties, zoals het verzenden van gebruikersmeldingen, in een regel met een lager aantal exemplaren (bijvoorbeeld 1-9).</span><span class="sxs-lookup"><span data-stu-id="5cf30-271">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="5cf30-272">En u gebruikt meer beperkende acties, zoals het beperken van de toegang tot inhoud zonder gebruikersoverschrijvingen toe te staan, in een regel met een hoger aantal exemplaren (bijvoorbeeld 10-any).</span><span class="sxs-lookup"><span data-stu-id="5cf30-272">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![Instantietellingen in de regeleditor](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="5cf30-274">Match nauwkeurigheid</span><span class="sxs-lookup"><span data-stu-id="5cf30-274">Match accuracy</span></span>

<span data-ttu-id="5cf30-275">Zoals hierboven beschreven, wordt een gevoelig informatietype gedefinieerd en gedetecteerd met behulp van een combinatie van verschillende soorten bewijsmateriaal.</span><span class="sxs-lookup"><span data-stu-id="5cf30-275">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="5cf30-276">Gewoonlijk wordt een gevoelig informatietype gedefinieerd door meerdere van dergelijke combinaties, patronen genoemd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-276">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="5cf30-277">Een patroon dat minder bewijs vereist, heeft een lagere overeenkomstnauwkeurigheid (of betrouwbaarheidsniveau), terwijl een patroon dat meer bewijs vereist, een hogere overeenkomstnauwkeurigheid (of betrouwbaarheidsniveau) heeft.</span><span class="sxs-lookup"><span data-stu-id="5cf30-277">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="5cf30-278">Zie Entiteitsdefinities voor gevoelige informatietype voor meer informatie over de werkelijke patronen en [betrouwbaarheidsniveaus die](sensitive-information-type-entity-definitions.md)door elk type gevoelige informatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="5cf30-278">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>
  
<span data-ttu-id="5cf30-279">Het gevoelige informatietype met de naam Creditcardnummer wordt bijvoorbeeld gedefinieerd door twee patronen:</span><span class="sxs-lookup"><span data-stu-id="5cf30-279">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="5cf30-280">Een patroon met 65% vertrouwen dat vereist:</span><span class="sxs-lookup"><span data-stu-id="5cf30-280">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="5cf30-281">Een nummer in de notatie van een creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="5cf30-281">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="5cf30-282">Een nummer dat de controlesom passeert.</span><span class="sxs-lookup"><span data-stu-id="5cf30-282">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="5cf30-283">Een patroon met 85% vertrouwen dat vereist:</span><span class="sxs-lookup"><span data-stu-id="5cf30-283">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="5cf30-284">Een nummer in de notatie van een creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="5cf30-284">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="5cf30-285">Een nummer dat de controlesom passeert.</span><span class="sxs-lookup"><span data-stu-id="5cf30-285">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="5cf30-286">Een trefwoord of een vervaldatum in de juiste indeling.</span><span class="sxs-lookup"><span data-stu-id="5cf30-286">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="5cf30-287">U kunt deze betrouwbaarheidsniveaus (of overeenkomstnauwkeurigheid) gebruiken in uw regels.</span><span class="sxs-lookup"><span data-stu-id="5cf30-287">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="5cf30-288">Meestal gebruikt u minder beperkende acties, zoals het verzenden van gebruikersmeldingen, in een regel met een lagere overeenkomstnauwkeurigheid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-288">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="5cf30-289">En u gebruikt meer beperkende acties, zoals het beperken van de toegang tot inhoud zonder gebruikersoverschrijvingen toe te staan, in een regel met een hogere overeenkomstnauwkeurigheid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-289">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="5cf30-290">Het is belangrijk om te begrijpen dat wanneer een specifiek type gevoelige informatie, zoals een creditcardnummer, inhoudelijk wordt geïdentificeerd, slechts één betrouwbaarheidsniveau wordt geretourneerd:</span><span class="sxs-lookup"><span data-stu-id="5cf30-290">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="5cf30-291">Als alle overeenkomsten voor één patroon zijn, wordt het betrouwbaarheidsniveau voor dat patroon geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-291">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="5cf30-292">Als er overeenkomsten zijn voor meer dan één patroon (dat wil gezegd, er zijn overeenkomsten met twee verschillende vertrouwensniveaus), wordt een betrouwbaarheidsniveau geretourneerd dat hoger is dan een van de afzonderlijke patronen alleen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-292">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="5cf30-293">Dit is het lastige deel.</span><span class="sxs-lookup"><span data-stu-id="5cf30-293">This is the tricky part.</span></span> <span data-ttu-id="5cf30-294">Als bijvoorbeeld voor een creditcard zowel de patronen van 65% als die van 85% overeenkomen, is het betrouwbaarheidsniveau dat wordt geretourneerd voor dat gevoelige informatietype groter dan 90%, omdat meer bewijs meer vertrouwen betekent.</span><span class="sxs-lookup"><span data-stu-id="5cf30-294">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="5cf30-295">Dus als u twee wederzijds exclusieve regels voor creditcards wilt maken, één voor de 65% overeenkomstnauwkeurigheid en één voor de 85% matchnauwkeurigheid, zouden de bereiken voor matchnauwkeurigheid er als volgt uitzien.</span><span class="sxs-lookup"><span data-stu-id="5cf30-295">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="5cf30-296">De eerste regel pikt alleen overeenkomsten op van het 65%-patroon.</span><span class="sxs-lookup"><span data-stu-id="5cf30-296">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="5cf30-297">De tweede regel pikt wedstrijden op met **ten minste één** match van 85% en kan mogelijk andere wedstrijden met een lager vertrouwen **hebben.**</span><span class="sxs-lookup"><span data-stu-id="5cf30-297">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![Twee regels met verschillende bereiken voor wedstrijdnauwkeurigheid](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="5cf30-299">Om deze redenen zijn de richtlijnen voor het maken van regels met verschillende overeenkomstnauwkeurigheden:</span><span class="sxs-lookup"><span data-stu-id="5cf30-299">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="5cf30-300">Het laagste betrouwbaarheidsniveau gebruikt meestal dezelfde waarde voor **min** en **max** (geen bereik).</span><span class="sxs-lookup"><span data-stu-id="5cf30-300">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="5cf30-301">Het hoogste betrouwbaarheidsniveau is meestal een bereik van net boven het lagere betrouwbaarheidsniveau tot 100.</span><span class="sxs-lookup"><span data-stu-id="5cf30-301">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="5cf30-302">Alle tussenvertrouwensniveaus variëren meestal van net boven het lagere betrouwbaarheidsniveau tot net onder het hogere betrouwbaarheidsniveau.</span><span class="sxs-lookup"><span data-stu-id="5cf30-302">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="5cf30-303">Een retentielabel gebruiken als voorwaarde in een DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="5cf30-303">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="5cf30-304">Wanneer u een eerder gemaakt en gepubliceerd [bewaarlabel](retention.md#retention-labels) gebruikt als voorwaarde in een DLP-beleid, zijn er enkele dingen waar u op moet letten:</span><span class="sxs-lookup"><span data-stu-id="5cf30-304">When you use a previously created and published [retention label](retention.md#retention-labels) as a condition in a DLP policy, there are some things to be aware of:</span></span>

- <span data-ttu-id="5cf30-305">Het bewaarlabel moet worden gemaakt en gepubliceerd voordat u het probeert te gebruiken als voorwaarde in een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-305">The retention label must be created and published before you attempt to use it as a condition in a DLP policy.</span></span>
- <span data-ttu-id="5cf30-306">Het synchroniseren van gepubliceerde bewaarlabels kan één tot zeven dagen duren. Zie [Wanneer bewaarlabels beschikbaar komen voor het aanvragen van bewaarlabels](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) die zijn gepubliceerd in een bewaarbeleid, en [Hoe lang het duurt voordat bewaarlabels van kracht worden](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) voor bewaarlabels die automatisch worden gepubliceerd, voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-306">Published retention labels can take from one to seven days to sync. For more information, see [When retention labels become available to apply](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) for retention labels published in a retention policy, and [How long it takes for retention labels to take effect](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) for retention labels that are auto-published.</span></span>
- <span data-ttu-id="5cf30-307">Het gebruik van een bewaarlabel in een beleid \*\* wordt alleen ondersteund voor items in SharePoint en OneDrive\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="5cf30-307">Using a retention label in a policy \*\*is only supported for items in SharePoint and OneDrive\*\*\*.</span></span>

  ![Labels als voorwaarde](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  <span data-ttu-id="5cf30-309">U kunt een bewaarlabel gebruiken in een DLP-beleid als u items hebt die onder retentie en dispositie staan, en u wilt er ook andere besturingselementen op toepassen, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5cf30-309">You might want to use a retention label in a DLP policy if you have items that are under retention and disposition, and you also want to apply other controls to them, for example:</span></span>

  - <span data-ttu-id="5cf30-310">U hebt een bewaarlabel met de naam **belastingjaar 2018** gepubliceerd, dat, wanneer toegepast op belastingdocumenten uit 2018 die zijn opgeslagen in SharePoint ze 10 jaar bewaart en vervolgens vervreemdt.</span><span class="sxs-lookup"><span data-stu-id="5cf30-310">You published a retention label named **tax year 2018**, which when applied to tax documents from 2018 that are stored in SharePoint retains them for 10 years then disposes of them.</span></span> <span data-ttu-id="5cf30-311">U wilt ook niet dat deze items buiten uw organisatie worden gedeeld, wat u kunt doen met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-311">You also don't want those items being shared outside your organization, which you can do with a DLP policy.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="5cf30-312">U krijgt deze fout als u een bewaarlabel opgeeft als voorwaarde in een DLP-beleid en u ook Exchange en/of Teams als locatie opneemt: **'Het beveiligen van gelabelde inhoud in e-mail- en teamberichten wordt niet ondersteund. Verwijder het onderstaande label of schakel Exchange en Teams uit als locatie."**</span><span class="sxs-lookup"><span data-stu-id="5cf30-312">You'll get this error if you specify a retention label as a condition in a DLP policy and you also include Exchange and/or Teams as a location: **"Protecting labeled content in email and teams messages isn't supported. Either remove the label below or turn off Exchange and Teams as a location."**</span></span> <span data-ttu-id="5cf30-313">Dit komt omdat Exchange transport de metagegevens van het label niet evalueert tijdens het verzenden en bezorgen van berichten.</span><span class="sxs-lookup"><span data-stu-id="5cf30-313">This is because Exchange transport does not evaluate the label metadata during message submission and delivery.</span></span> 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="5cf30-314">Een gevoeligheidslabel gebruiken als voorwaarde in een DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="5cf30-314">Using a sensitivity label as a condition in a DLP policy</span></span>

<span data-ttu-id="5cf30-315">[Meer informatie](./dlp-sensitivity-label-as-condition.md) over het gebruik van het gevoeligheids label als voorwaarde in DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-315">[Learn more](./dlp-sensitivity-label-as-condition.md) about using Sensitivity label as a condition in DLP policies.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="5cf30-316">Hoe deze functie zich verhoudt tot andere functies</span><span class="sxs-lookup"><span data-stu-id="5cf30-316">How this feature relates to other features</span></span>

<span data-ttu-id="5cf30-317">Verschillende functies kunnen worden toegepast op inhoud die gevoelige informatie bevat:</span><span class="sxs-lookup"><span data-stu-id="5cf30-317">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="5cf30-318">Een [bewaarlabel en een bewaarbeleid](retention.md) kunnen beide **bewaaracties afdwingen** voor deze inhoud.</span><span class="sxs-lookup"><span data-stu-id="5cf30-318">A [retention label and a retention policy](retention.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="5cf30-319">Een DLP-beleid kan **beveiligingsacties** voor deze inhoud afdwingen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-319">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="5cf30-320">En voordat u deze acties afdwingt, kan een DLP-beleid vereisen dat aan andere voorwaarden wordt voldaan naast de inhoud die een label bevat.</span><span class="sxs-lookup"><span data-stu-id="5cf30-320">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![Diagram met functies die van toepassing kunnen zijn op gevoelige informatie](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="5cf30-322">Houd er rekening mee dat een DLP-beleid een rijkere detectie mogelijkheid heeft dan een label of bewaar beleid dat wordt toegepast op gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-322">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="5cf30-323">Een DLP-beleid kan beschermende acties afdwingen voor inhoud die gevoelige informatie bevat, en als de gevoelige informatie uit de inhoud wordt verwijderd, worden deze beschermende acties ongedaan gemaakt de volgende keer dat de inhoud wordt gescand.</span><span class="sxs-lookup"><span data-stu-id="5cf30-323">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="5cf30-324">Maar als een bewaarbeleid of -label wordt toegepast op inhoud die gevoelige informatie bevat, is dat een eenmalige actie die niet ongedaan wordt gemaakt, zelfs niet als de gevoelige informatie wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-324">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="5cf30-325">Door een label als voorwaarde te gebruiken in een DLP-beleid, kunt u zowel bewaar- als beveiligingsacties afdwingen op inhoud met dat label.</span><span class="sxs-lookup"><span data-stu-id="5cf30-325">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="5cf30-326">U kunt denken aan inhoud die een label bevat dat precies lijkt op inhoud die gevoelige informatie bevat - zowel een label als een gevoelig informatietype zijn eigenschappen die worden gebruikt om inhoud te classificeren, zodat u acties op die inhoud kunt afdwingen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-326">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![Diagram van DLP-beleid met label als voorwaarde](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="5cf30-328">Eenvoudige instellingen versus geavanceerde instellingen</span><span class="sxs-lookup"><span data-stu-id="5cf30-328">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="5cf30-329">Wanneer u een DLP-beleid maakt, kunt u kiezen tussen eenvoudige of geavanceerde instellingen:</span><span class="sxs-lookup"><span data-stu-id="5cf30-329">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="5cf30-330">**Eenvoudige instellingen** maken het eenvoudig om het meest voorkomende type DLP-beleid te maken zonder de regeleditor te gebruiken om regels te maken of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-330">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="5cf30-331">**Geavanceerde instellingen** gebruiken de regeleditor om u volledige controle te geven over elke instelling voor uw DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-331">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="5cf30-332">Maak je geen zorgen, onder de covers werken eenvoudige instellingen en geavanceerde instellingen precies hetzelfde, door regels af te dwingen die bestaan uit voorwaarden en acties - alleen met eenvoudige instellingen zie je de regeleditor niet.</span><span class="sxs-lookup"><span data-stu-id="5cf30-332">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions—only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="5cf30-333">Het is een snelle manier om een DLP-beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="5cf30-333">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="5cf30-334">Eenvoudige instellingen</span><span class="sxs-lookup"><span data-stu-id="5cf30-334">Simple settings</span></span>

<span data-ttu-id="5cf30-335">Verreweg het meest voorkomende DLP-scenario is het maken van een beleid om te voorkomen dat inhoud met gevoelige informatie wordt gedeeld met mensen buiten uw organisatie, en het uitvoeren van een automatische herstelactie, zoals het beperken van wie toegang heeft tot de inhoud, het verzenden van meldingen van eindgebruikers of beheerders en het controleren van de gebeurtenis voor later onderzoek.</span><span class="sxs-lookup"><span data-stu-id="5cf30-335">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remediating action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="5cf30-336">Mensen gebruiken DLP om onbedoelde openbaarmaking van gevoelige informatie te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-336">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="5cf30-337">Als u dit doel wilt vereenvoudigen, kunt u bij het maken van een DLP-beleid **eenvoudige instellingen** gebruiken kiezen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-337">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="5cf30-338">Deze instellingen bieden alles wat u nodig hebt om het meest voorkomende DLP-beleid te implementeren, zonder dat u naar de regeleditor hoeft te gaan.</span><span class="sxs-lookup"><span data-stu-id="5cf30-338">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![DLP-opties voor eenvoudige en geavanceerde instellingen](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="5cf30-340">Geavanceerde instellingen</span><span class="sxs-lookup"><span data-stu-id="5cf30-340">Advanced settings</span></span>

<span data-ttu-id="5cf30-341">Als u meer aangepast DLP-beleid wilt maken, kunt u **Geavanceerde instellingen gebruiken** kiezen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-341">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="5cf30-342">De geavanceerde instellingen bieden u de regeleditor, waar u volledige controle hebt over elke mogelijke optie, inclusief het aantal exemplaren en de nauwkeurigheid van de overeenkomst (betrouwbaarheidsniveau) voor elke regel.</span><span class="sxs-lookup"><span data-stu-id="5cf30-342">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="5cf30-343">Als u snel naar een sectie wilt gaan, klikt u op een item in de bovenste navigatie van de regeleditor om naar die sectie hieronder te gaan.</span><span class="sxs-lookup"><span data-stu-id="5cf30-343">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![Bovenste navigatiemenu van DLP-regeleditor](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="5cf30-345">DLP-beleidssjablonen</span><span class="sxs-lookup"><span data-stu-id="5cf30-345">DLP policy templates</span></span>

<span data-ttu-id="5cf30-346">De eerste stap bij het maken van een DLP-beleid is het kiezen van welke informatie moet worden beschermd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-346">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="5cf30-347">Door te beginnen met een DLP-sjabloon, slaat u het werk op van het helemaal opnieuw bouwen van een nieuwe set regels en het uitzoeken welke soorten informatie standaard moeten worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-347">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="5cf30-348">U kunt deze vereisten vervolgens toevoegen of wijzigen om de regel af te stemmen op de specifieke vereisten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-348">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="5cf30-349">Een vooraf geconfigureerde DLP-beleidssjabloon kan u helpen specifieke soorten gevoelige informatie te detecteren, zoals HIPAA-gegevens, PCI-DSS-gegevens, Gramm-Leach-Bliley Act-gegevens of zelfs landespecifieke persoonlijk identificeerbare informatie (P.I.).</span><span class="sxs-lookup"><span data-stu-id="5cf30-349">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="5cf30-350">Om het u gemakkelijk te maken om veelvoorkomende typen gevoelige informatie te vinden en te beschermen, bevatten de beleidssjablonen in Microsoft 365 al de meest voorkomende typen gevoelige informatie die nodig zijn om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="5cf30-350">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Microsoft 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![Lijst met sjablonen voor beleid ter voorkoming van gegevensverlies met de focus op sjabloon voor de Amerikaanse Patriot Act](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="5cf30-352">Uw organisatie kan ook zijn eigen specifieke vereisten hebben, in welk geval u een DLP-beleid helemaal opnieuw kunt maken door de optie **Aangepast beleid te** kiezen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-352">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="5cf30-353">Een aangepast beleid is leeg en bevat geen vooraf gemaakte regels.</span><span class="sxs-lookup"><span data-stu-id="5cf30-353">A custom policy is empty and contains no premade rules.</span></span> 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a><span data-ttu-id="5cf30-354">DLP-rapporten</span><span class="sxs-lookup"><span data-stu-id="5cf30-354">DLP reports</span></span>

<span data-ttu-id="5cf30-355">Nadat u uw DLP-beleid hebt gemaakt en ingeschakeld, wilt u controleren of ze werken zoals u hebt bedoeld en u helpen compliant te blijven.</span><span class="sxs-lookup"><span data-stu-id="5cf30-355">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="5cf30-356">Met DLP-rapporten kunt u snel het aantal DLP-beleids- en regelovereenkomsten in de loop van de tijd bekijken, en het aantal valse positieven en overschrijvingen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-356">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="5cf30-357">Voor elk rapport kunt u deze overeenkomsten filteren op locatie, tijdsbestek en zelfs beperken tot een specifiek beleid, regel of actie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-357">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="5cf30-358">Met de DLP-rapporten kunt u zakelijke inzichten krijgen en:</span><span class="sxs-lookup"><span data-stu-id="5cf30-358">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="5cf30-359">Focus op specifieke tijdsperiodes en begrijp de redenen voor pieken en trends.</span><span class="sxs-lookup"><span data-stu-id="5cf30-359">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="5cf30-360">Ontdek bedrijfsprocessen die in strijd zijn met het nalevingsbeleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-360">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="5cf30-361">Begrijp de zakelijke impact van het DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-361">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="5cf30-362">Daarnaast kunt u de DLP-rapporten gebruiken om uw DLP-beleid te verfijnen terwijl u ze uitvoert.</span><span class="sxs-lookup"><span data-stu-id="5cf30-362">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![Rapportendashboard in beveiligings- en compliancecentrum](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="5cf30-364">Hoe DLP-beleid werkt</span><span class="sxs-lookup"><span data-stu-id="5cf30-364">How DLP policies work</span></span>

<span data-ttu-id="5cf30-365">DLP detecteert gevoelige informatie met behulp van diepgaande inhoudsanalyse (niet alleen een eenvoudige tekstscan).</span><span class="sxs-lookup"><span data-stu-id="5cf30-365">DLP detects sensitive information by using deep content analysis (not just a simple text scan).</span></span> <span data-ttu-id="5cf30-366">Deze analyse van diepe inhoud maakt gebruik van trefwoordovereenkomsten, woordenboekovereenkomsten, de evaluatie van reguliere expressies, interne functies en andere methoden om inhoud te detecteren die overeenkomt met uw DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-366">This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies.</span></span> <span data-ttu-id="5cf30-367">Mogelijk wordt slechts een klein percentage van uw gegevens als gevoelig beschouwd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-367">Potentially only a small percentage of your data is considered sensitive.</span></span> <span data-ttu-id="5cf30-368">Een DLP-beleid kan alleen die gegevens identificeren, bewaken en automatisch beschermen, zonder mensen te belemmeren of te beïnvloeden die met de rest van uw inhoud werken.</span><span class="sxs-lookup"><span data-stu-id="5cf30-368">A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="5cf30-369">Beleid wordt gesynchroniseerd</span><span class="sxs-lookup"><span data-stu-id="5cf30-369">Policies are synced</span></span>

<span data-ttu-id="5cf30-370">Nadat u een DLP-beleid hebt gemaakt in het Security &amp; Compliance Center, wordt het opgeslagen in een centraal beleids archief en vervolgens gesynchroniseerd met de verschillende inhouds bronnen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="5cf30-370">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="5cf30-371">Exchange Online, en van daaruit naar Outlook op het web en Outlook.</span><span class="sxs-lookup"><span data-stu-id="5cf30-371">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
    
- <span data-ttu-id="5cf30-372">OneDrive voor Bedrijven sites.</span><span class="sxs-lookup"><span data-stu-id="5cf30-372">OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="5cf30-373">SharePoint Online sites.</span><span class="sxs-lookup"><span data-stu-id="5cf30-373">SharePoint Online sites.</span></span>
    
- <span data-ttu-id="5cf30-374">Office bureaubladprogramma's (Excel, PowerPoint en Word).</span><span class="sxs-lookup"><span data-stu-id="5cf30-374">Office desktop programs (Excel, PowerPoint, and Word).</span></span>

- <span data-ttu-id="5cf30-375">Microsoft Teams kanalen en chatberichten.</span><span class="sxs-lookup"><span data-stu-id="5cf30-375">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="5cf30-376">Nadat het beleid is gesynchroniseerd met de juiste locaties, wordt de inhoud geëvalueerd en acties afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-376">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="5cf30-377">Beleidsevaluatie in OneDrive voor Bedrijven en SharePoint Online sites</span><span class="sxs-lookup"><span data-stu-id="5cf30-377">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="5cf30-378">Op al uw SharePoint online sites en OneDrive voor Bedrijven sites veranderen documenten voortdurend - ze worden voortdurend gemaakt, bewerkt, gedeeld, enzovoort.</span><span class="sxs-lookup"><span data-stu-id="5cf30-378">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="5cf30-379">Dit betekent dat documenten op elk gewenst moment conflicteren of compatibel worden met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-379">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="5cf30-380">Een persoon kan bijvoorbeeld een document uploaden dat geen gevoelige informatie bevat naar zijn teamsite, maar later kan een andere persoon hetzelfde document bewerken en er gevoelige informatie aan toevoegen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-380">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="5cf30-381">Daarom controleren DLP-beleidsdocumenten regelmatig op beleidsovereenkomsten op de achtergrond.</span><span class="sxs-lookup"><span data-stu-id="5cf30-381">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="5cf30-382">U kunt dit zien als asynchrone beleidsevaluatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-382">You can think of this as asynchronous policy evaluation.</span></span>
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a><span data-ttu-id="5cf30-383">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="5cf30-383">How it works</span></span>
 
<span data-ttu-id="5cf30-384">Wanneer mensen documenten toevoegen of wijzigen op hun sites, scant de zoekmachine de inhoud, zodat u er later naar kunt zoeken.</span><span class="sxs-lookup"><span data-stu-id="5cf30-384">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="5cf30-385">Terwijl dit gebeurt, wordt de inhoud ook gescand op gevoelige informatie en om te controleren of deze wordt gedeeld.</span><span class="sxs-lookup"><span data-stu-id="5cf30-385">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="5cf30-386">Alle gevoelige informatie die wordt gevonden, wordt veilig opgeslagen in de zoekindex, zodat alleen het nalevingsteam er toegang toe heeft, maar geen typische gebruikers.</span><span class="sxs-lookup"><span data-stu-id="5cf30-386">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="5cf30-387">Elk DLP-beleid dat u hebt ingeschakeld, wordt op de achtergrond uitgevoerd (asynchroon), controleert regelmatig zoekopdrachten naar inhoud die overeenkomt met een beleid en past acties toe om het te beschermen tegen onbedoelde lekken.</span><span class="sxs-lookup"><span data-stu-id="5cf30-387">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![Diagram met de manier waarop DLP-beleid inhoud asynchroon evalueert](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording -->
<span data-ttu-id="5cf30-389">Ten slotte kunnen documenten conflicteren met een DLP-beleid, maar ze kunnen ook compatibel worden met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-389">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy.</span></span> <span data-ttu-id="5cf30-390">Als een persoon bijvoorbeeld creditcardnummers aan een document toevoegt, kan dit ertoe leiden dat een DLP-beleid de toegang tot het document automatisch blokkeert.</span><span class="sxs-lookup"><span data-stu-id="5cf30-390">For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically.</span></span> <span data-ttu-id="5cf30-391">Maar als de persoon later de gevoelige informatie verwijdert, wordt de actie (in dit geval blokkeren) automatisch ongedaan gemaakt de volgende keer dat het document wordt geëvalueerd aan de hand van het beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-391">But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="5cf30-392">DLP evalueert alle inhoud die kan worden geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-392">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="5cf30-393">Zie [Standaard verkende bestandsextensies en geparseerde bestandstypen in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)voor meer informatie over welke bestandstypen standaard worden gecrawld.</span><span class="sxs-lookup"><span data-stu-id="5cf30-393">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>

> [!NOTE]
> <span data-ttu-id="5cf30-394">Om te voorkomen dat documenten worden gedeeld voordat DLP-beleid de mogelijkheid had om ze te analyseren, kan het delen van nieuwe bestanden in SharePoint worden geblokkeerd totdat de inhoud ervan is geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="5cf30-394">In order to prevent documents from being shared before DLP policies had the opportunity to analyze them, sharing of new files in SharePoint can be blocked until its content has been indexed.</span></span> <span data-ttu-id="5cf30-395">Zie [nieuwe bestanden standaard als gevoelig markeren](/sharepoint/sensitive-by-default) voor gedetailleerde informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-395">See, [Mark new files as sensitive by default](/sharepoint/sensitive-by-default) for detailed information.</span></span> 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="5cf30-396">Beleidsevaluatie in Exchange Online, Outlook en Outlook op het web</span><span class="sxs-lookup"><span data-stu-id="5cf30-396">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="5cf30-397">Wanneer u een DLP-beleid maakt dat Exchange Online als locatie bevat, wordt het beleid gesynchroniseerd van het Office 365 Security &amp; Compliance Center naar Exchange Online en vervolgens van Exchange Online naar Outlook op het web en Outlook.</span><span class="sxs-lookup"><span data-stu-id="5cf30-397">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="5cf30-398">Wanneer een bericht wordt samengesteld in Outlook, kan de gebruiker beleidstips zien wanneer de inhoud die wordt gemaakt, wordt geëvalueerd aan de hand van DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-398">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="5cf30-399">En nadat een bericht is verzonden, wordt het geëvalueerd aan de hand van DLP-beleid als een normaal onderdeel van de e-mail stroom, samen met Exchange e-mail stroom regels (ook wel transport regels) en DLP-beleid gemaakt in het Exchange beheer center.</span><span class="sxs-lookup"><span data-stu-id="5cf30-399">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="5cf30-400">DLP-beleid scant zowel het bericht als eventuele bijlagen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-400">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="5cf30-401">Beleidsevaluatie in de Office desktopprogramma's</span><span class="sxs-lookup"><span data-stu-id="5cf30-401">Policy evaluation in the Office desktop programs</span></span>

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
<span data-ttu-id="5cf30-402">Excel, PowerPoint en Word bevatten dezelfde mogelijkheid om gevoelige informatie te identificeren en DLP-beleid toe te passen als SharePoint online en OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="5cf30-402">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="5cf30-403">Deze Office programma's hun DLP-beleid rechtstreeks vanuit het centrale beleids archief synchroniseren en vervolgens de inhoud voortdurend evalueren ten opzichte van het DLP-beleid wanneer mensen werken met documenten die zijn geopend vanaf een site die is opgenomen in een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="5cf30-403">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="5cf30-404">DLP-beleidsevaluatie in Office is ontworpen om geen invloed te hebben op de prestaties van de programma's of de productiviteit van mensen die aan inhoud werken.</span><span class="sxs-lookup"><span data-stu-id="5cf30-404">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="5cf30-405">Als ze aan een groot document werken of als de computer van de gebruiker bezet is, kan het enkele seconden duren voordat een beleidstip wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5cf30-405">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="5cf30-406">Beleidsevaluatie in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5cf30-406">Policy evaluation in Microsoft Teams</span></span>
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

<span data-ttu-id="5cf30-407">Wanneer u een DLP-beleid maakt dat Microsoft Teams als locatie bevat, wordt het beleid gesynchroniseerd van het Office 365 Security &amp; Compliance Center naar gebruikersaccounts en Microsoft Teams kanalen en chatberichten.</span><span class="sxs-lookup"><span data-stu-id="5cf30-407">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="5cf30-408">Afhankelijk van hoe DLP-beleid is geconfigureerd, kan het bericht worden geblokkeerd of ingetrokken wanneer iemand probeert gevoelige informatie te delen in een Microsoft Teams chat- of kanaalbericht.</span><span class="sxs-lookup"><span data-stu-id="5cf30-408">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="5cf30-409">En documenten die gevoelige informatie bevatten en die worden gedeeld met gasten (externe gebruikers) worden niet geopend voor die gebruikers.</span><span class="sxs-lookup"><span data-stu-id="5cf30-409">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="5cf30-410">Zie Preventie [van gegevensverlies en Microsoft Teams](dlp-microsoft-teams.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-410">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="5cf30-411">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="5cf30-411">Permissions</span></span>

<span data-ttu-id="5cf30-412">Leden van uw nalevingsteam die DLP-beleid maken, hebben machtigingen nodig voor het Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="5cf30-412">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="5cf30-413">Uw Tenant beheerder heeft standaard toegang tot deze locatie en kan nalevings functionarissen en andere mensen toegang geven tot het Security &amp; Compliance Center, zonder hen alle machtigingen van een Tenant beheerder te geven. Om dit te doen, raden wij u aan:</span><span class="sxs-lookup"><span data-stu-id="5cf30-413">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="5cf30-414">Maak een groep in Microsoft 365 en voeg er nalevingsfunctionarissen aan toe.</span><span class="sxs-lookup"><span data-stu-id="5cf30-414">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="5cf30-415">Maak een rolgroep op de pagina **Machtigingen** van het Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="5cf30-415">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="5cf30-416">Gebruik tijdens het maken van de rolgroep de sectie **Rollen kiezen** om de volgende rol toe te voegen aan de rolgroep: **DLP Compliance Management**.</span><span class="sxs-lookup"><span data-stu-id="5cf30-416">While creating the role group, use the **Choose Roles** section to add the following role to the Role Group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="5cf30-417">Gebruik de sectie **Leden kiezen** om de Microsoft 365 groep die u eerder hebt gemaakt, toe te voegen aan de rolgroep.</span><span class="sxs-lookup"><span data-stu-id="5cf30-417">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="5cf30-418">U kunt ook een rolgroep maken met alleen-weergeven bevoegdheden voor het DLP-beleid en DLP-rapporten door de rol **Alleen-weergeven DLP-nalevingsbeheer** toe te kennen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-418">You can also create a role group with view-only privileges to the DLP policies and DLP reports by granting the **View-Only DLP Compliance Management** role.</span></span>

<span data-ttu-id="5cf30-419">Zie [Gebruikers toegang geven tot het Office 365 Compliance Center voor](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5cf30-419">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="5cf30-420">Deze machtigingen zijn alleen vereist om een DLP-beleid te maken en toe te passen.</span><span class="sxs-lookup"><span data-stu-id="5cf30-420">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="5cf30-421">Voor beleidshandhaving is geen toegang tot de inhoud vereist.</span><span class="sxs-lookup"><span data-stu-id="5cf30-421">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="5cf30-422">Zoek de DLP cmdlets</span><span class="sxs-lookup"><span data-stu-id="5cf30-422">Find the DLP cmdlets</span></span>

<span data-ttu-id="5cf30-423">Als u de meeste cmdlets voor het Security &amp; Compliance Center wilt gebruiken, moet u het als beste doen:</span><span class="sxs-lookup"><span data-stu-id="5cf30-423">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. <span data-ttu-id="5cf30-424">[Verbinding maken naar de Office 365 Beveiliging &amp; Compliance Center met behulp van externe PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="5cf30-424">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="5cf30-425">Gebruik een van deze [beleids- en nalevings-dlp-cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span><span class="sxs-lookup"><span data-stu-id="5cf30-425">Use any of these [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span></span>
    
<span data-ttu-id="5cf30-426">DLP-rapporten moeten echter gegevens uit Microsoft 365 halen, inclusief Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5cf30-426">However, DLP reports need pull data from across Microsoft 365, including Exchange Online.</span></span> <span data-ttu-id="5cf30-427">Daarom zijn **de cmdlets voor de DLP-rapporten beschikbaar in Exchange Online Powershell - niet in &amp; Powershell van Security Compliance Center**.</span><span class="sxs-lookup"><span data-stu-id="5cf30-427">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="5cf30-428">Als u de cmdlets voor de DLP-rapporten wilt gebruiken, moet u daarom het als u het eerst gebruiken:</span><span class="sxs-lookup"><span data-stu-id="5cf30-428">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. <span data-ttu-id="5cf30-429">[Maak verbinding met Exchange Online via externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5cf30-429">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="5cf30-430">Gebruik een van deze cmdlets voor de DLP-rapporten:</span><span class="sxs-lookup"><span data-stu-id="5cf30-430">Use any of these cmdlets for the DLP reports:</span></span>
    
    - [<span data-ttu-id="5cf30-431">Get-DlpDetectionsRapport</span><span class="sxs-lookup"><span data-stu-id="5cf30-431">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [<span data-ttu-id="5cf30-432">Get-DlpDetailRapport</span><span class="sxs-lookup"><span data-stu-id="5cf30-432">Get-DlpDetailReport</span></span>](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a><span data-ttu-id="5cf30-433">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="5cf30-433">More information</span></span>

- [<span data-ttu-id="5cf30-434">Een DLP-beleid maken vanuit een sjabloon</span><span class="sxs-lookup"><span data-stu-id="5cf30-434">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="5cf30-435">Meldingen verzenden en beleidstips voor DLP-beleid weergeven</span><span class="sxs-lookup"><span data-stu-id="5cf30-435">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="5cf30-436">Een DLP-beleid maken om documenten te beveiligen met FCI of andere eigenschappen</span><span class="sxs-lookup"><span data-stu-id="5cf30-436">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="5cf30-437">Wat zijn de DLP-beleidssjablonen?</span><span class="sxs-lookup"><span data-stu-id="5cf30-437">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="5cf30-438">Definities van entiteiten van het type vertrouwelijke gegevens</span><span class="sxs-lookup"><span data-stu-id="5cf30-438">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="5cf30-439">Doel van de DLP-functies</span><span class="sxs-lookup"><span data-stu-id="5cf30-439">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="5cf30-440">Een aangepast type gevoelige informatie maken</span><span class="sxs-lookup"><span data-stu-id="5cf30-440">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
