---
title: Verwijzing naar preventie van gegevensverlies
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
description: referentiemateriaal voor preventie van gegevensverlies
ms.openlocfilehash: 5c01b6419a9af100cfaedccbd5a9c4923ca3e42f
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061792"
---
# <a name="data-loss-prevention-reference"></a><span data-ttu-id="eac14-103">Verwijzing naar preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="eac14-103">Data loss prevention reference</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="eac14-104">Dit onderwerp is niet langer de belangrijkste bron voor het voorkomen Microsoft 365 gegevensverlies (DLP).</span><span class="sxs-lookup"><span data-stu-id="eac14-104">This is reference topic is no longer the main resource for Microsoft 365 data loss prevention (DLP) information.</span></span> <span data-ttu-id="eac14-105">De DLP-inhoudsset wordt bijgewerkt en geherstructureerd.</span><span class="sxs-lookup"><span data-stu-id="eac14-105">The DLP content set is being updated and restructured.</span></span> <span data-ttu-id="eac14-106">De onderwerpen die in dit artikel worden besproken, worden verplaatst naar nieuwe, bijgewerkte artikelen.</span><span class="sxs-lookup"><span data-stu-id="eac14-106">The topics covered in this article will be moving to new, updated articles.</span></span> <span data-ttu-id="eac14-107">Zie Meer informatie over preventie van [gegevensverlies](dlp-learn-about-dlp.md)voor meer informatie over DLP.</span><span class="sxs-lookup"><span data-stu-id="eac14-107">For more information about DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> <span data-ttu-id="eac14-108">Mogelijkheden voor preventie van gegevensverlies zijn onlangs toegevoegd aan Microsoft Teams chat- en kanaalberichten voor gebruikers met een licentie voor Office 365 Advanced Compliance, die beschikbaar is als zelfstandige optie en is opgenomen in Office 365 E5 en Microsoft 365 E5 Compliance.</span><span class="sxs-lookup"><span data-stu-id="eac14-108">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="eac14-109">Zie voor meer informatie over licentievereisten [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="eac14-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>



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
## <a name="create-and-manage-dlp-policies"></a><span data-ttu-id="eac14-110">DLP-beleid maken en beheren</span><span class="sxs-lookup"><span data-stu-id="eac14-110">Create and manage DLP policies</span></span>

<span data-ttu-id="eac14-111">U maakt en beheert DLP-beleid op de pagina Preventie van gegevensverlies in het Microsoft 365 Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="eac14-111">You create and manage DLP policies on the Data loss prevention page in the Microsoft 365 Compliance center.</span></span>
  
![Pagina preventie van gegevensverlies in het Office 365 Beveiligings &amp; compliancecentrum](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
<span data-ttu-id="eac14-113">U kunt een regel gebruiken om aan een specifieke beveiligingsvereiste te voldoen en vervolgens een DLP-beleid gebruiken om gemeenschappelijke beveiligingsvereisten samen te stellen, zoals alle regels die nodig zijn om te voldoen aan een specifieke verordening.</span><span class="sxs-lookup"><span data-stu-id="eac14-113">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="eac14-114">U hebt bijvoorbeeld een DLP-beleid waarmee u de aanwezigheid kunt detecteren van informatie die is onderworpen aan de Health Insurance Portability and Accountability Act (HIPAA).</span><span class="sxs-lookup"><span data-stu-id="eac14-114">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="eac14-115">Dit DLP-beleid kan helpen bij het beveiligen van HIPAA-gegevens (het wat) op alle SharePoint Online-sites en alle OneDrive voor Bedrijven-sites (waar) door te zoeken naar een document met deze gevoelige informatie dat wordt gedeeld met personen buiten uw organisatie (de voorwaarden) en vervolgens de toegang tot het document te blokkeren en een melding te verzenden (de acties).</span><span class="sxs-lookup"><span data-stu-id="eac14-115">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="eac14-116">Deze vereisten worden opgeslagen als afzonderlijke regels en gegroepeerd als een DLP-beleid om beheer en rapportage te vereenvoudigen.</span><span class="sxs-lookup"><span data-stu-id="eac14-116">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![Diagram toont aan dat DLP-beleid locaties en regels bevat](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
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

<span data-ttu-id="eac14-118">Als u ervoor kiest om specifieke distributiegroepen op te nemen in Exchange, is het DLP-beleid alleen van toepassing op de leden van die groep.</span><span class="sxs-lookup"><span data-stu-id="eac14-118">If you choose to include specific distribution groups in Exchange, the DLP policy will be scoped only to the members of that group.</span></span> <span data-ttu-id="eac14-119">Als u een distributiegroep uitsluit, worden alle leden van die distributiegroep uitgesloten van beleidsevaluatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-119">Similarly excluding a distribution group will exclude all the members of that distribution group from policy evaluation.</span></span> <span data-ttu-id="eac14-120">U kunt ervoor kiezen om een beleid uit te breiden naar de leden van distributielijsten, dynamische distributiegroepen en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="eac14-120">You can choose to scope a policy to the members of distribution lists, dynamic distribution groups, and security groups.</span></span> <span data-ttu-id="eac14-121">Een DLP-beleid mag niet meer dan 50 dergelijke insluitsels en uitsluitingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="eac14-121">A DLP policy can contain no more than 50 such inclusions and exclusions.</span></span>

<span data-ttu-id="eac14-122">Als u ervoor kiest om specifieke sites op te nemen SharePoint uit te sluiten, kan een DLP-beleid niet meer dan 100 dergelijke insluitingen en uitsluitingen bevatten.</span><span class="sxs-lookup"><span data-stu-id="eac14-122">If you choose to include or exclude specific SharePoint sites, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="eac14-123">Hoewel deze limiet bestaat, kunt u deze limiet overschrijden door een beleid voor de hele organisatie toe te passen of een beleid dat van toepassing is op hele locaties.</span><span class="sxs-lookup"><span data-stu-id="eac14-123">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>

<span data-ttu-id="eac14-124">Als u ervoor kiest om specifieke OneDrive accounts of groepen op te nemen of uit te sluiten, kan een DLP-beleid niet meer dan 100 gebruikersaccounts of 50 groepen bevatten als opname of uitsluiting.</span><span class="sxs-lookup"><span data-stu-id="eac14-124">If you choose to include or exclude specific OneDrive accounts or groups, a DLP policy can contain no more than 100 user accounts or 50 groups as inclusion or exclusion.</span></span>
  
### <a name="rules"></a><span data-ttu-id="eac14-125">Regels</span><span class="sxs-lookup"><span data-stu-id="eac14-125">Rules</span></span>

> [!NOTE]
> <span data-ttu-id="eac14-126">Het standaardgedrag van een DLP-beleid, wanneer er geen waarschuwing is geconfigureerd, is niet om te waarschuwen of te activeren.</span><span class="sxs-lookup"><span data-stu-id="eac14-126">The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger.</span></span> <span data-ttu-id="eac14-127">Dit geldt alleen voor standaardinformatietypen.</span><span class="sxs-lookup"><span data-stu-id="eac14-127">This applies only to default information types.</span></span> <span data-ttu-id="eac14-128">Voor aangepaste informatietypen wordt het systeem gewaarschuwd, zelfs als er geen actie is gedefinieerd in het beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-128">For custom information types, the system will alert even if there is no action defined in the policy.</span></span>

<span data-ttu-id="eac14-129">Regels dwingen uw zakelijke vereisten af op de inhoud van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-129">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="eac14-130">Een beleid bevat een of meer regels en elke regel bestaat uit voorwaarden en acties.</span><span class="sxs-lookup"><span data-stu-id="eac14-130">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="eac14-131">Voor elke regel worden de acties automatisch ondernomen wanneer aan de voorwaarden wordt voldaan.</span><span class="sxs-lookup"><span data-stu-id="eac14-131">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="eac14-132">Regels worden opeenvolgend uitgevoerd, te beginnen met de regel met de hoogste prioriteit in elk beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-132">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="eac14-133">Een regel bevat ook opties om gebruikers (met beleidstips en e-mailmeldingen) en beheerders (met e-mailincidentrapporten) te laten weten dat inhoud aan de regel is afgestemd.</span><span class="sxs-lookup"><span data-stu-id="eac14-133">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="eac14-134">Hier vindt u de onderdelen van een regel, die hieronder worden uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="eac14-134">Here are the components of a rule, each explained below.</span></span>
  
![Secties van de DLP-regeleditor](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="eac14-136">Voorwaarden</span><span class="sxs-lookup"><span data-stu-id="eac14-136">Conditions</span></span>

<span data-ttu-id="eac14-137">Voorwaarden zijn belangrijk omdat ze bepalen welke soorten gegevens u zoekt en wanneer u een actie moet ondernemen.</span><span class="sxs-lookup"><span data-stu-id="eac14-137">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="eac14-138">U kunt er bijvoorbeeld voor kiezen om inhoud met paspoortnummers te negeren, tenzij de inhoud meer dan 10 dergelijke getallen bevat en wordt gedeeld met personen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-138">For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="eac14-139">Voorwaarden zijn gericht op **de inhoud,** zoals welke typen gevoelige informatie u zoekt, en ook op de **context,** zoals met wie het document wordt gedeeld.</span><span class="sxs-lookup"><span data-stu-id="eac14-139">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="eac14-140">U kunt voorwaarden gebruiken om verschillende acties toe te wijzen aan verschillende risiconiveaus.</span><span class="sxs-lookup"><span data-stu-id="eac14-140">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="eac14-141">Gevoelige inhoud die intern wordt gedeeld, kan bijvoorbeeld een lager risico hebben en minder acties vereisen dan gevoelige inhoud die wordt gedeeld met personen buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-141">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![Lijst met beschikbare DLP-voorwaarden](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="eac14-143">De voorwaarden die nu beschikbaar zijn, kunnen bepalen of:</span><span class="sxs-lookup"><span data-stu-id="eac14-143">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="eac14-144">Inhoud bevat een type gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-144">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="eac14-145">Inhoud bevat een label.</span><span class="sxs-lookup"><span data-stu-id="eac14-145">Content contains a label.</span></span> <span data-ttu-id="eac14-146">Zie de onderstaande sectie Een bewaarlabel gebruiken als voorwaarde [in een DLP-beleid](#using-a-retention-label-as-a-condition-in-a-dlp-policy)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-146">For more information, see the below section [Using a retention label as a condition in a DLP policy](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="eac14-147">Inhoud wordt gedeeld met personen buiten of binnen uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-147">Content is shared with people outside or inside your organization.</span></span>

  > [!NOTE]
  > <span data-ttu-id="eac14-148">Gebruikers die niet-gastaccounts hebben in de Active Directory- of Azure Active Directory tenant van een hostorganisatie, worden beschouwd als personen binnen de organisatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-148">Users who have non-guest accounts in a host organization's Active Directory or Azure Active Directory tenant are considered as people inside the organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="eac14-149">Typen gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="eac14-149">Types of sensitive information</span></span>

<span data-ttu-id="eac14-150">Met een DLP-beleid wordt gevoelige informatie beschermd, die is gedefinieerd als een **type gevoelige informatie**.</span><span class="sxs-lookup"><span data-stu-id="eac14-150">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="eac14-151">Microsoft 365 bevat definities voor veelvoorkomende typen gevoelige informatie in veel verschillende regio's die u kunt gebruiken, zoals een creditcardnummer, bankrekeningnummers, nationale id-nummers en paspoortnummers.</span><span class="sxs-lookup"><span data-stu-id="eac14-151">Microsoft 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![Lijst met beschikbare typen gevoelige informatie](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="eac14-153">Wanneer in een DLP-beleid wordt op zoek naar een type gevoelige informatie, zoals een creditcardnummer, wordt er niet alleen naar een 16-cijferig getal op zoek.</span><span class="sxs-lookup"><span data-stu-id="eac14-153">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="eac14-154">Elk type gevoelige informatie wordt gedefinieerd en gedetecteerd met behulp van een combinatie van:</span><span class="sxs-lookup"><span data-stu-id="eac14-154">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="eac14-155">Trefwoorden.</span><span class="sxs-lookup"><span data-stu-id="eac14-155">Keywords.</span></span>
    
- <span data-ttu-id="eac14-156">Interne functies om checksums of samenstelling te valideren.</span><span class="sxs-lookup"><span data-stu-id="eac14-156">Internal functions to validate checksums or composition.</span></span>
    
- <span data-ttu-id="eac14-157">Evaluatie van reguliere expressies om patronen te zoeken.</span><span class="sxs-lookup"><span data-stu-id="eac14-157">Evaluation of regular expressions to find pattern matches.</span></span>
    
- <span data-ttu-id="eac14-158">Ander inhoudsonderzoek.</span><span class="sxs-lookup"><span data-stu-id="eac14-158">Other content examination.</span></span>
    
<span data-ttu-id="eac14-159">Dit helpt DLP-detectie om een hoge mate van nauwkeurigheid te bereiken en tegelijkertijd het aantal fout-positieven te verminderen dat het werk van personen kan onderbreken.</span><span class="sxs-lookup"><span data-stu-id="eac14-159">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="eac14-160">Acties</span><span class="sxs-lookup"><span data-stu-id="eac14-160">Actions</span></span>

<span data-ttu-id="eac14-161">Wanneer inhoud overeenkomt met een voorwaarde in een regel, kunt u acties toepassen om de inhoud automatisch te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="eac14-161">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![Lijst met beschikbare DLP-acties](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="eac14-163">Met de acties die nu beschikbaar zijn, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="eac14-163">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="eac14-164">**Toegang tot de inhoud beperken** Afhankelijk van uw behoefte kunt u de toegang tot inhoud op drie manieren beperken:</span><span class="sxs-lookup"><span data-stu-id="eac14-164">**Restrict access to the content** Depending on your need, you can restrict access to content in three ways:</span></span>

  1. <span data-ttu-id="eac14-165">Toegang tot inhoud beperken voor iedereen.</span><span class="sxs-lookup"><span data-stu-id="eac14-165">Restrict access to content for everyone.</span></span>
  2. <span data-ttu-id="eac14-166">De toegang tot inhoud beperken voor personen buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-166">Restrict access to content for people outside the organization.</span></span>
  3. <span data-ttu-id="eac14-167">De toegang beperken tot 'Iedereen met de koppeling'.</span><span class="sxs-lookup"><span data-stu-id="eac14-167">Restrict access to "Anyone with the link."</span></span>

  <span data-ttu-id="eac14-168">Voor site-inhoud betekent dit dat machtigingen voor het document voor iedereen zijn beperkt, behalve de beheerder van de primaire siteverzameling, de eigenaar van het document en de persoon die het document het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="eac14-168">For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="eac14-169">Deze personen kunnen de gevoelige informatie uit het document verwijderen of andere herstelactie ondernemen.</span><span class="sxs-lookup"><span data-stu-id="eac14-169">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="eac14-170">Wanneer het document voldoet, worden de oorspronkelijke machtigingen automatisch hersteld.</span><span class="sxs-lookup"><span data-stu-id="eac14-170">When the document is in compliance, the original permissions are automatically restored.</span></span> <span data-ttu-id="eac14-171">Wanneer de toegang tot een document wordt geblokkeerd, wordt het document weergegeven met een speciaal beleidstippictogram in de bibliotheek op de site.</span><span class="sxs-lookup"><span data-stu-id="eac14-171">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
  ![Beleidstip waarin de toegang tot document wordt weergegeven, is geblokkeerd](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  <span data-ttu-id="eac14-173">Voor e-mailinhoud wordt met deze actie het bericht niet verzonden.</span><span class="sxs-lookup"><span data-stu-id="eac14-173">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="eac14-174">Afhankelijk van hoe de DLP-regel is geconfigureerd, ziet de afzender een NDR of (als de regel een melding gebruikt) een beleidstip en/of e-mailmelding.</span><span class="sxs-lookup"><span data-stu-id="eac14-174">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
  ![Waarschuwing dat niet-geautoriseerde geadresseerden uit het bericht moeten worden verwijderd](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="eac14-176">Gebruikersmeldingen en gebruikers overschrijven</span><span class="sxs-lookup"><span data-stu-id="eac14-176">User notifications and user overrides</span></span>

<span data-ttu-id="eac14-177">U kunt meldingen en overschrijven gebruiken om uw gebruikers te informeren over DLP-beleid en hen te helpen compatibel te blijven zonder hun werk te blokkeren.</span><span class="sxs-lookup"><span data-stu-id="eac14-177">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="eac14-178">Als een gebruiker bijvoorbeeld een document met gevoelige informatie probeert te delen, kan een DLP-beleid hen zowel een e-mailmelding sturen als een beleidstip laten zien in de context van de documentbibliotheek, zodat ze het beleid kunnen overschrijven als ze een zakelijke rechtvaardiging hebben.</span><span class="sxs-lookup"><span data-stu-id="eac14-178">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![Gebruikersmeldingen en gebruikers overschrijven secties van DLP-regeleditor](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="eac14-180">De e-mail kan de persoon op de hoogte stellen die de inhoud heeft verzonden, gedeeld of voor het laatst heeft gewijzigd en, voor site-inhoud, de primaire beheerder van de siteverzameling en de eigenaar van het document.</span><span class="sxs-lookup"><span data-stu-id="eac14-180">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="eac14-181">Daarnaast kunt u wie u ook kiest uit de e-mailmelding toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="eac14-181">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="eac14-182">Naast het verzenden van een e-mailmelding, wordt in een gebruikersmelding ook een beleidstip weergegeven:</span><span class="sxs-lookup"><span data-stu-id="eac14-182">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="eac14-183">In Outlook en webversie van Outlook.</span><span class="sxs-lookup"><span data-stu-id="eac14-183">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="eac14-184">Voor het document op een SharePoint Online of OneDrive voor Bedrijven site.</span><span class="sxs-lookup"><span data-stu-id="eac14-184">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="eac14-185">In Excel, PowerPoint en Word, wanneer het document is opgeslagen op een site die is opgenomen in een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-185">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="eac14-186">In de e-mailmelding en beleidstip wordt uitgelegd waarom inhoud in strijd is met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-186">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="eac14-187">Als u kiest, kunnen gebruikers met de e-mailmelding en beleidstip een regel overschrijven door een fout-positief te melden of een zakelijke rechtvaardiging te geven.</span><span class="sxs-lookup"><span data-stu-id="eac14-187">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="eac14-188">Hiermee kunt u gebruikers informeren over uw DLP-beleid en afdwingen zonder dat mensen hun werk kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="eac14-188">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="eac14-189">Informatie over overschrijven en fout-positieven wordt ook geregistreerd voor rapportage (zie hieronder over de DLP-rapporten) en opgenomen in de incidentenrapporten (volgende sectie), zodat de compliance officer deze informatie regelmatig kan controleren.</span><span class="sxs-lookup"><span data-stu-id="eac14-189">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="eac14-190">Zo ziet een beleidstip eruit in een OneDrive voor Bedrijven account.</span><span class="sxs-lookup"><span data-stu-id="eac14-190">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![Beleidstip voor een document in een OneDrive account](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 <span data-ttu-id="eac14-192">Zie Meldingen en beleidstips gebruiken voor meer informatie over gebruikersmeldingen en beleidstips in [DLP-beleid.](use-notifications-and-policy-tips.md)</span><span class="sxs-lookup"><span data-stu-id="eac14-192">To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).</span></span>

#### <a name="alerts-and-incident-reports"></a><span data-ttu-id="eac14-193">Meldingen en incidentenrapporten</span><span class="sxs-lookup"><span data-stu-id="eac14-193">Alerts and Incident reports</span></span>

<span data-ttu-id="eac14-194">Wanneer een regel is afgestemd, kunt u een waarschuwings-e-mail verzenden naar uw compliance officer (of een persoon(s) die u kiest) met details van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="eac14-194">When a rule is matched, you can send an alert email to your compliance officer ( or any person(s) you choose) with details of the alert.</span></span> <span data-ttu-id="eac14-195">In dit waarschuwings-e-mailbericht wordt een koppeling van het [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) geplaatst, waar de compliance officer naar kan gaan om de details van waarschuwingen en gebeurtenissen te bekijken.</span><span class="sxs-lookup"><span data-stu-id="eac14-195">This alert email will carry a link of the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) which the compliance officer can go to view the details of alert and events.</span></span> <span data-ttu-id="eac14-196">Het dashboard bevat details van de gebeurtenis die de waarschuwing heeft geactiveerd, samen met de details van het overeenkomende DLP-beleid en de gevoelige inhoud die is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="eac14-196">The dashboard contains details of the event that triggered the alert along with details of the DLP policy matched and the sensitive content detected.</span></span>

<span data-ttu-id="eac14-197">Daarnaast kunt u ook een incidentrapport verzenden met details van de gebeurtenis.</span><span class="sxs-lookup"><span data-stu-id="eac14-197">In addition, you can also send an incident report with details of the event.</span></span> <span data-ttu-id="eac14-198">Dit rapport bevat informatie over het item dat is aangepast, de werkelijke inhoud die aan de regel is aangepast en de naam van de persoon die de inhoud het laatst heeft gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="eac14-198">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="eac14-199">Voor e-mailberichten bevat het rapport ook als bijlage het oorspronkelijke bericht dat overeenkomt met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-199">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eac14-200">![Pagina voor het configureren van incidentenrapporten](../media/Alerts-and-incident-report.png)</span><span class="sxs-lookup"><span data-stu-id="eac14-200">![Page for configuring incident reports](../media/Alerts-and-incident-report.png)</span></span>

<span data-ttu-id="eac14-201">DLP scant e-mail anders dan items in SharePoint Online of OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="eac14-201">DLP scans email differently from items in SharePoint Online or OneDrive for Business.</span></span> <span data-ttu-id="eac14-202">In SharePoint Online en OneDrive voor Bedrijven, scant DLP bestaande items en nieuwe items en genereert een waarschuwings- en incidentrapport wanneer er een overeenkomst wordt gevonden.</span><span class="sxs-lookup"><span data-stu-id="eac14-202">In SharePoint Online and OneDrive for Business, DLP scans existing items as well as new ones and generates an alert and incident report whenever a match is found.</span></span> <span data-ttu-id="eac14-203">In Exchange Online DLP alleen nieuwe e-mailberichten scannen en een rapport genereren als er een beleidsmatch is.</span><span class="sxs-lookup"><span data-stu-id="eac14-203">In Exchange Online, DLP only scans new email messages and generates a report if there is a policy match.</span></span> <span data-ttu-id="eac14-204">DLP ***scant of*** komt niet overeen met eerder bestaande e-mailitems die zijn opgeslagen in een postvak of archief.</span><span class="sxs-lookup"><span data-stu-id="eac14-204">DLP ***does not*** scan or match previously existing email items that are stored in a mailbox or archive.</span></span>
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="eac14-205">Groeperings- en logische operatoren</span><span class="sxs-lookup"><span data-stu-id="eac14-205">Grouping and logical operators</span></span>

<span data-ttu-id="eac14-206">Vaak heeft uw DLP-beleid een eenvoudige vereiste, zoals het identificeren van alle inhoud die een Amerikaans sociaal-beveiligingsnummer bevat.</span><span class="sxs-lookup"><span data-stu-id="eac14-206">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="eac14-207">In andere scenario's moet uw DLP-beleid mogelijk meer los gedefinieerde gegevens identificeren.</span><span class="sxs-lookup"><span data-stu-id="eac14-207">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="eac14-208">Als u bijvoorbeeld inhoud wilt identificeren die is onderworpen aan de Amerikaanse Health Insurance Act (HIPAA), moet u zoeken naar:</span><span class="sxs-lookup"><span data-stu-id="eac14-208">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="eac14-209">Inhoud die specifieke typen gevoelige informatie bevat, zoals een Amerikaans nummer voor sociale zekerheid of een DEA-nummer (Drug Enforcement Agency).</span><span class="sxs-lookup"><span data-stu-id="eac14-209">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="eac14-210">EN</span><span class="sxs-lookup"><span data-stu-id="eac14-210">AND</span></span>
    
- <span data-ttu-id="eac14-211">Inhoud die moeilijker te identificeren is, zoals communicatie over de zorg van een patiënt of beschrijvingen van verstrekte medische services.</span><span class="sxs-lookup"><span data-stu-id="eac14-211">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="eac14-212">Het identificeren van deze inhoud vereist overeenkomende trefwoorden uit zeer grote trefwoordenlijsten, zoals de Internationale classificatie van ziektes (ICD-9-CM of ICD-10-CM).</span><span class="sxs-lookup"><span data-stu-id="eac14-212">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="eac14-213">U kunt dergelijke losjes gedefinieerde gegevens eenvoudig identificeren met behulp van groeperings- en logische operatoren (AND, OF).</span><span class="sxs-lookup"><span data-stu-id="eac14-213">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="eac14-214">Wanneer u een DLP-beleid maakt, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="eac14-214">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="eac14-215">Groep gevoelige informatietypen.</span><span class="sxs-lookup"><span data-stu-id="eac14-215">Group sensitive information types.</span></span>
    
- <span data-ttu-id="eac14-216">Kies de logische operator tussen de typen gevoelige informatie binnen een groep en tussen de groepen zelf.</span><span class="sxs-lookup"><span data-stu-id="eac14-216">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="eac14-217">De operator in een groep kiezen</span><span class="sxs-lookup"><span data-stu-id="eac14-217">Choosing the operator within a group</span></span>

<span data-ttu-id="eac14-218">In een groep kunt u kiezen of aan alle voorwaarden in die groep moet worden voldaan om de inhoud aan de regel te laten voldoen.</span><span class="sxs-lookup"><span data-stu-id="eac14-218">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![Groep met de operatoren in de groep](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="eac14-220">Een groep toevoegen</span><span class="sxs-lookup"><span data-stu-id="eac14-220">Adding a group</span></span>

<span data-ttu-id="eac14-221">U kunt snel een groep toevoegen, die zijn eigen voorwaarden en operator binnen die groep kan hebben.</span><span class="sxs-lookup"><span data-stu-id="eac14-221">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![Knop Groep toevoegen](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="eac14-223">De operator kiezen tussen groepen</span><span class="sxs-lookup"><span data-stu-id="eac14-223">Choosing the operator between groups</span></span>

<span data-ttu-id="eac14-224">Tussen groepen kunt u kiezen of aan de voorwaarden in slechts één groep of aan alle groepen moet worden voldaan om de inhoud aan de regel te laten voldoen.</span><span class="sxs-lookup"><span data-stu-id="eac14-224">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="eac14-225">Het ingebouwde AMERIKAANSE **HIPAA-beleid** heeft bijvoorbeeld een regel waarin een **AND-operator** tussen de groepen wordt gebruikt, zodat inhoud wordt geïdentificeerd die het volgende bevat:</span><span class="sxs-lookup"><span data-stu-id="eac14-225">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="eac14-226">van de **groep PII-id's** (ten minste één SSN-getal **OF DEA-getal)**</span><span class="sxs-lookup"><span data-stu-id="eac14-226">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="eac14-227">**EN**</span><span class="sxs-lookup"><span data-stu-id="eac14-227">**AND**</span></span>
    
- <span data-ttu-id="eac14-228">uit de groep **Medische voorwaarden** (ten minste één Trefwoord ICD-9-CM **OF** ICD-10-CM trefwoord)</span><span class="sxs-lookup"><span data-stu-id="eac14-228">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![Groepen met de operator tussen groepen](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="eac14-230">De prioriteit waarmee regels worden verwerkt</span><span class="sxs-lookup"><span data-stu-id="eac14-230">The priority by which rules are processed</span></span>

<span data-ttu-id="eac14-231">Wanneer u regels maakt in een beleid, krijgt elke regel een prioriteit toegewezen in de volgorde waarin deze is gemaakt, wat betekent dat de regel die eerst is gemaakt, de eerste prioriteit heeft, de regel die als tweede wordt gemaakt, een tweede prioriteit heeft, en ga zo maar door.</span><span class="sxs-lookup"><span data-stu-id="eac14-231">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eac14-232">![Regels in prioriteitsorde](../media/dlp-rules-in-priority-order.png)</span><span class="sxs-lookup"><span data-stu-id="eac14-232">![Rules in priority order](../media/dlp-rules-in-priority-order.png)</span></span>
  
<span data-ttu-id="eac14-233">Nadat u meer dan één DLP-beleid hebt ingesteld, kunt u de prioriteit van een of meer beleidsregels wijzigen.</span><span class="sxs-lookup"><span data-stu-id="eac14-233">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="eac14-234">Als u dat wilt doen, selecteert u een beleid, kiest u **Beleid bewerken** en gebruikt u de lijst **Prioriteit** om de prioriteit op te geven.</span><span class="sxs-lookup"><span data-stu-id="eac14-234">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eac14-235">![Prioriteit instellen voor een beleid](../media/dlp-set-policy-priority.png)</span><span class="sxs-lookup"><span data-stu-id="eac14-235">![Set priority for a policy](../media/dlp-set-policy-priority.png)</span></span>

<span data-ttu-id="eac14-236">Wanneer inhoud wordt geëvalueerd op basis van regels, worden de regels in prioriteitsorder verwerkt.</span><span class="sxs-lookup"><span data-stu-id="eac14-236">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="eac14-237">Als inhoud overeenkomt met meerdere regels, worden de regels in prioriteitsorder verwerkt en wordt de meest beperkende actie afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="eac14-237">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="eac14-238">Als inhoud bijvoorbeeld overeenkomt met alle volgende regels, wordt regel 3 afgedwongen omdat deze de hoogste prioriteit heeft, de meest beperkende regel:</span><span class="sxs-lookup"><span data-stu-id="eac14-238">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="eac14-239">Regel 1: geeft alleen een bericht aan gebruikers</span><span class="sxs-lookup"><span data-stu-id="eac14-239">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="eac14-240">Regel 2: geeft gebruikers een bericht, beperkt de toegang en staat gebruikers overschrijven toe</span><span class="sxs-lookup"><span data-stu-id="eac14-240">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="eac14-241">Regel 3: geeft gebruikers een bericht, beperkt de toegang en staat niet toe dat gebruikers worden overschrijven</span><span class="sxs-lookup"><span data-stu-id="eac14-241">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="eac14-242">Regel 4: geeft alleen een bericht aan gebruikers</span><span class="sxs-lookup"><span data-stu-id="eac14-242">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="eac14-243">Regel 5: beperkt de toegang</span><span class="sxs-lookup"><span data-stu-id="eac14-243">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="eac14-244">Regel 6: geeft gebruikers een bericht, beperkt de toegang en staat niet toe dat gebruikers worden overschrijven</span><span class="sxs-lookup"><span data-stu-id="eac14-244">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="eac14-245">Houd er in dit voorbeeld rekening mee dat overeenkomsten voor alle regels worden opgenomen in de auditlogboeken en worden weergegeven in de DLP-rapporten, ook al wordt alleen de meest beperkende regel afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="eac14-245">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="eac14-246">Wat beleidstips betreft, moet u er rekening mee dat:</span><span class="sxs-lookup"><span data-stu-id="eac14-246">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="eac14-247">Alleen de beleidstip van de hoogste prioriteit, de meest beperkende regel, wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="eac14-247">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="eac14-248">Een beleidstip van een regel die toegang tot inhoud blokkeert, wordt bijvoorbeeld weergegeven via een beleidstip van een regel die alleen een melding verzendt.</span><span class="sxs-lookup"><span data-stu-id="eac14-248">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="eac14-249">Dit voorkomt dat personen een trapsgepunt met beleidstips zien.</span><span class="sxs-lookup"><span data-stu-id="eac14-249">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="eac14-250">Als de beleidstips in de meest beperkende regel toestaan dat personen de regel overschrijven, worden ook andere regels overgenomen die overeenkomen met de inhoud door deze regel te vervangen.</span><span class="sxs-lookup"><span data-stu-id="eac14-250">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="eac14-251">Regels afstemmen om ze gemakkelijker of moeilijker te matchen</span><span class="sxs-lookup"><span data-stu-id="eac14-251">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="eac14-252">Nadat personen hun DLP-beleid hebben aan- en in- of uit te voeren, lopen ze soms tegen de volgende problemen aan:</span><span class="sxs-lookup"><span data-stu-id="eac14-252">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="eac14-253">Te veel inhoud die **geen gevoelige informatie is,** komt overeen met de regels, met andere woorden te veel fout-positieven.</span><span class="sxs-lookup"><span data-stu-id="eac14-253">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="eac14-254">Te weinig inhoud die **gevoelige informatie is, komt** overeen met de regels.</span><span class="sxs-lookup"><span data-stu-id="eac14-254">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="eac14-255">Met andere woorden, de beschermende acties worden niet afgedwongen op de gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-255">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="eac14-256">Als u deze problemen wilt oplossen, kunt u uw regels afstemmen door het aantal exemplaren en de nauwkeurigheid van de exemplaren aan te passen, zodat inhoud moeilijker of gemakkelijker aan de regels kan voldoen.</span><span class="sxs-lookup"><span data-stu-id="eac14-256">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="eac14-257">Elk type gevoelige informatie dat in een regel wordt gebruikt, heeft zowel een aantal exemplaren als een overeenkomende nauwkeurigheid.</span><span class="sxs-lookup"><span data-stu-id="eac14-257">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="eac14-258">Aantal exemplaren</span><span class="sxs-lookup"><span data-stu-id="eac14-258">Instance count</span></span>

<span data-ttu-id="eac14-259">Aantal exemplaren betekent gewoon hoeveel exemplaren van een specifiek type gevoelige informatie aanwezig moeten zijn om inhoud aan de regel te kunnen laten overeenkomen.</span><span class="sxs-lookup"><span data-stu-id="eac14-259">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="eac14-260">Inhoud komt bijvoorbeeld overeen met de regel die hieronder wordt weergegeven als tussen 1 en 9 unieke V.S. of Vk.</span><span class="sxs-lookup"><span data-stu-id="eac14-260">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="eac14-261">paspoortnummers worden geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="eac14-261">passport numbers are identified.</span></span>

> [!NOTE]
> <span data-ttu-id="eac14-262">Het aantal exemplaren bevat alleen **unieke** overeenkomsten voor gevoelige informatietypen en trefwoorden.</span><span class="sxs-lookup"><span data-stu-id="eac14-262">The instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="eac14-263">Als een e-mailbericht bijvoorbeeld 10 exemplaren van hetzelfde creditcardnummer bevat, tellen die tien exemplaren als één exemplaar van een creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="eac14-263">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span>
  
<span data-ttu-id="eac14-264">Als u het aantal exemplaren wilt gebruiken om regels af te stemmen, is de richtlijn eenvoudig:</span><span class="sxs-lookup"><span data-stu-id="eac14-264">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="eac14-265">Als u de regel gemakkelijker wilt matchen, verlaagt u het **aantal minuten** en/of verhoogt u het **maximum** aantal.</span><span class="sxs-lookup"><span data-stu-id="eac14-265">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="eac14-266">U kunt ook **max instellen** op **elke** waarde door de numerieke waarde te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="eac14-266">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="eac14-267">Als u de regel moeilijker wilt matchen, verhoogt u het **aantal minuten.**</span><span class="sxs-lookup"><span data-stu-id="eac14-267">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="eac14-268">Meestal gebruikt u minder beperkende acties, zoals het verzenden van gebruikersmeldingen, in een regel met een lager aantal exemplaren (bijvoorbeeld 1-9).</span><span class="sxs-lookup"><span data-stu-id="eac14-268">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="eac14-269">En u gebruikt meer beperkende acties, zoals het beperken van de toegang tot inhoud zonder dat gebruikers overschrijven toestaan, in een regel met een hoger aantal exemplaren (bijvoorbeeld 10-any).</span><span class="sxs-lookup"><span data-stu-id="eac14-269">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![Aantal exemplaren in de regeleditor](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="eac14-271">Nauwkeurigheid overeenkomen</span><span class="sxs-lookup"><span data-stu-id="eac14-271">Match accuracy</span></span>

<span data-ttu-id="eac14-272">Zoals hierboven beschreven, wordt een type gevoelige informatie gedefinieerd en gedetecteerd met behulp van een combinatie van verschillende typen bewijs.</span><span class="sxs-lookup"><span data-stu-id="eac14-272">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="eac14-273">Meestal wordt een type gevoelige informatie gedefinieerd door meerdere dergelijke combinaties, patronen genoemd.</span><span class="sxs-lookup"><span data-stu-id="eac14-273">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="eac14-274">Een patroon dat minder bewijs vereist, heeft een lagere nauwkeurigheid (of betrouwbaarheidsniveau), terwijl een patroon dat meer bewijs vereist, een hogere nauwkeurigheid (of betrouwbaarheidsniveau) heeft.</span><span class="sxs-lookup"><span data-stu-id="eac14-274">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="eac14-275">Zie Entiteitsdefinities van het type Gevoelige informatie voor meer informatie over de werkelijke patronen en betrouwbaarheidsniveaus die door elk type gevoelige [informatie worden gebruikt.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="eac14-275">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>
  
<span data-ttu-id="eac14-276">Het type gevoelige informatie met de naam Creditcardnummer wordt bijvoorbeeld gedefinieerd door twee patronen:</span><span class="sxs-lookup"><span data-stu-id="eac14-276">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="eac14-277">Een patroon met 65% vertrouwen dat vereist is:</span><span class="sxs-lookup"><span data-stu-id="eac14-277">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="eac14-278">Een getal in de notatie van een creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="eac14-278">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="eac14-279">Een getal dat de checksum passeert.</span><span class="sxs-lookup"><span data-stu-id="eac14-279">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="eac14-280">Een patroon met 85% vertrouwen dat vereist is:</span><span class="sxs-lookup"><span data-stu-id="eac14-280">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="eac14-281">Een getal in de notatie van een creditcardnummer.</span><span class="sxs-lookup"><span data-stu-id="eac14-281">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="eac14-282">Een getal dat de checksum passeert.</span><span class="sxs-lookup"><span data-stu-id="eac14-282">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="eac14-283">Een trefwoord of een vervaldatum in de juiste notatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-283">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="eac14-284">U kunt deze betrouwbaarheidsniveaus (of overeenkomende nauwkeurigheid) gebruiken in uw regels.</span><span class="sxs-lookup"><span data-stu-id="eac14-284">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="eac14-285">Meestal gebruikt u minder beperkende acties, zoals het verzenden van gebruikersmeldingen, in een regel met een lagere nauwkeurigheid.</span><span class="sxs-lookup"><span data-stu-id="eac14-285">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="eac14-286">En u gebruikt meer beperkende acties, zoals het beperken van de toegang tot inhoud zonder dat gebruikers overschrijven toestaan, in een regel met een hogere nauwkeurigheid.</span><span class="sxs-lookup"><span data-stu-id="eac14-286">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="eac14-287">Het is belangrijk om te begrijpen dat wanneer een specifiek type gevoelige informatie, zoals een creditcardnummer, in inhoud wordt geïdentificeerd, slechts één betrouwbaarheidsniveau wordt geretourneerd:</span><span class="sxs-lookup"><span data-stu-id="eac14-287">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="eac14-288">Als alle overeenkomsten één patroon hebben, wordt het betrouwbaarheidsniveau voor dat patroon geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="eac14-288">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="eac14-289">Als er overeenkomsten zijn voor meer dan één patroon (dat wil zeggen dat er overeenkomsten zijn met twee verschillende betrouwbaarheidsniveaus), wordt een betrouwbaarheidsniveau hoger dan een van de afzonderlijke patronen alleen geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="eac14-289">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="eac14-290">Dit is het lastige gedeelte.</span><span class="sxs-lookup"><span data-stu-id="eac14-290">This is the tricky part.</span></span> <span data-ttu-id="eac14-291">Als voor een creditcard bijvoorbeeld zowel de patronen van 65% als 85% overeenkomen, is het betrouwbaarheidsniveau dat voor dat gevoelige informatietype wordt geretourneerd, groter dan 90%, omdat meer bewijs meer vertrouwen betekent.</span><span class="sxs-lookup"><span data-stu-id="eac14-291">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="eac14-292">Als u dus twee regels wilt maken die elkaar uitsluiten voor creditcards, een voor de nauwkeurigheid van 65% en een voor de 85% overeenkomstnauwkeurigheid, ziet het bereik voor overeenkomende nauwkeurigheid er zo uit.</span><span class="sxs-lookup"><span data-stu-id="eac14-292">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="eac14-293">De eerste regel haalt alleen overeenkomsten op van het 65%-patroon.</span><span class="sxs-lookup"><span data-stu-id="eac14-293">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="eac14-294">De tweede regel haalt overeenkomsten op met ten minste  **één** overeenkomst van 85% en kan mogelijk andere overeenkomsten met een lager vertrouwen hebben.</span><span class="sxs-lookup"><span data-stu-id="eac14-294">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![Twee regels met verschillende bereik voor overeenkomende nauwkeurigheid](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="eac14-296">Om deze redenen is de richtlijn voor het maken van regels met verschillende overeenkomstnauwkeurigheid:</span><span class="sxs-lookup"><span data-stu-id="eac14-296">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="eac14-297">Het laagste betrouwbaarheidsniveau gebruikt meestal dezelfde waarde voor **min** en **max** (geen bereik).</span><span class="sxs-lookup"><span data-stu-id="eac14-297">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="eac14-298">Het hoogste betrouwbaarheidsniveau is meestal een bereik van net boven het lagere betrouwbaarheidsniveau tot 100.</span><span class="sxs-lookup"><span data-stu-id="eac14-298">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="eac14-299">Alle tussen betrouwbaarheidsniveaus variëren meestal van net boven het lagere betrouwbaarheidsniveau tot net onder het hogere betrouwbaarheidsniveau.</span><span class="sxs-lookup"><span data-stu-id="eac14-299">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="eac14-300">Een retentielabel gebruiken als voorwaarde in een DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="eac14-300">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="eac14-301">Wanneer u een eerder [](retention.md#retention-labels) gemaakt en gepubliceerd bewaarlabel gebruikt als voorwaarde in een DLP-beleid, zijn er enkele dingen waar u rekening mee moet houden:</span><span class="sxs-lookup"><span data-stu-id="eac14-301">When you use a previously created and published [retention label](retention.md#retention-labels) as a condition in a DLP policy, there are some things to be aware of:</span></span>

- <span data-ttu-id="eac14-302">Het bewaarlabel moet worden gemaakt en gepubliceerd voordat u het probeert te gebruiken als voorwaarde in een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-302">The retention label must be created and published before you attempt to use it as a condition in a DLP policy.</span></span>
- <span data-ttu-id="eac14-303">Het kan één tot zeven dagen duren voordat gepubliceerde bewaarlabels worden gesynchroniseerd. Zie Wanneer bewaarlabels beschikbaar zijn om bewaarlabels toe te [](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) passen die zijn gepubliceerd in een bewaarbeleid, en Hoe lang het duurt voordat bewaarlabels van kracht worden voor bewaarlabels die automatisch worden gepubliceerd. [](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply)</span><span class="sxs-lookup"><span data-stu-id="eac14-303">Published retention labels can take from one to seven days to sync. For more information, see [When retention labels become available to apply](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) for retention labels published in a retention policy, and [How long it takes for retention labels to take effect](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) for retention labels that are auto-published.</span></span>
- <span data-ttu-id="eac14-304">Het gebruik van een bewaarlabel in een beleid **wordt alleen ondersteund voor items in SharePoint en OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="eac14-304">Using a retention label in a policy \*\*is only supported for items in SharePoint and OneDrive\*\*\*.</span></span>

  ![Labels als voorwaarde](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  <span data-ttu-id="eac14-306">Mogelijk wilt u een bewaarlabel gebruiken in een DLP-beleid als u items hebt die onder bewaring en dispositie staan en u ook andere besturingselementen op deze items wilt toepassen, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="eac14-306">You might want to use a retention label in a DLP policy if you have items that are under retention and disposition, and you also want to apply other controls to them, for example:</span></span>

  - <span data-ttu-id="eac14-307">U hebt een bewaarlabel met de naam belastingjaar **2018** gepubliceerd, dat na toepassing op belastingdocumenten uit 2018 die zijn opgeslagen in SharePoint deze 10 jaar behoudt en vervolgens wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="eac14-307">You published a retention label named **tax year 2018**, which when applied to tax documents from 2018 that are stored in SharePoint retains them for 10 years then disposes of them.</span></span> <span data-ttu-id="eac14-308">U wilt ook niet dat deze items buiten uw organisatie worden gedeeld, wat u kunt doen met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-308">You also don't want those items being shared outside your organization, which you can do with a DLP policy.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="eac14-309">Deze fout wordt weergegeven als u een bewaarlabel opgeeft als voorwaarde in een DLP-beleid en u ook Exchange en/of Teams opgeeft als locatie: 'Het beveiligen van gelabelde inhoud in e-mail- en teamsberichten wordt niet **ondersteund. Verwijder het label hieronder of schakel Exchange en Teams als locatie uit.'**</span><span class="sxs-lookup"><span data-stu-id="eac14-309">You'll get this error if you specify a retention label as a condition in a DLP policy and you also include Exchange and/or Teams as a location: **"Protecting labeled content in email and teams messages isn't supported. Either remove the label below or turn off Exchange and Teams as a location."**</span></span> <span data-ttu-id="eac14-310">Dit komt omdat Exchange tijdens het verzenden en bezorgen van berichten de metagegevens van het label niet evalueert.</span><span class="sxs-lookup"><span data-stu-id="eac14-310">This is because Exchange transport does not evaluate the label metadata during message submission and delivery.</span></span> 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="eac14-311">Een gevoeligheidslabel gebruiken als voorwaarde in een DLP-beleid</span><span class="sxs-lookup"><span data-stu-id="eac14-311">Using a sensitivity label as a condition in a DLP policy</span></span>

<span data-ttu-id="eac14-312">[Meer informatie over](./dlp-sensitivity-label-as-condition.md) het gebruik van gevoeligheidslabels als voorwaarde in DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-312">[Learn more](./dlp-sensitivity-label-as-condition.md) about using Sensitivity label as a condition in DLP policies.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="eac14-313">Hoe deze functie zich verhoudt tot andere functies</span><span class="sxs-lookup"><span data-stu-id="eac14-313">How this feature relates to other features</span></span>

<span data-ttu-id="eac14-314">Er kunnen verschillende functies worden toegepast op inhoud die gevoelige informatie bevat:</span><span class="sxs-lookup"><span data-stu-id="eac14-314">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="eac14-315">Een [bewaarlabel en een bewaarbeleid kunnen](retention.md) beide **bewaaracties** voor deze inhoud afdwingen.</span><span class="sxs-lookup"><span data-stu-id="eac14-315">A [retention label and a retention policy](retention.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="eac14-316">Met een DLP-beleid kunnen **beveiligingsacties voor** deze inhoud worden afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="eac14-316">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="eac14-317">En voordat u deze acties afdwingt, kan een DLP-beleid vereisen dat aan andere voorwaarden moet worden voldaan, naast de inhoud die een label bevat.</span><span class="sxs-lookup"><span data-stu-id="eac14-317">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![Diagram met functies die van toepassing kunnen zijn op gevoelige informatie](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="eac14-319">Houd er rekening mee dat een DLP-beleid een uitgebreidere detectiemogelijkheid heeft dan een label- of bewaarbeleid dat is toegepast op gevoelige informatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-319">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="eac14-320">Een DLP-beleid kan beschermende acties afdwingen voor inhoud die gevoelige informatie bevat. Als de gevoelige informatie uit de inhoud wordt verwijderd, worden deze beschermende acties ongedaan gemaakt wanneer de inhoud de volgende keer wordt gescand.</span><span class="sxs-lookup"><span data-stu-id="eac14-320">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="eac14-321">Maar als een bewaarbeleid of label wordt toegepast op inhoud die gevoelige informatie bevat, is dat een een-time actie die niet ongedaan wordt gemaakt, zelfs niet als de gevoelige informatie wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="eac14-321">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="eac14-322">Door een label te gebruiken als voorwaarde in een DLP-beleid, kunt u zowel bewaaracties als beschermingsacties afdwingen op inhoud met dat label.</span><span class="sxs-lookup"><span data-stu-id="eac14-322">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="eac14-323">U kunt denken aan inhoud die een label bevat, precies zoals inhoud die gevoelige informatie bevat. Zowel een label als een type gevoelige informatie zijn eigenschappen die worden gebruikt om inhoud te classificeren, zodat u acties op die inhoud kunt afdwingen.</span><span class="sxs-lookup"><span data-stu-id="eac14-323">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![Diagram van DLP-beleid met label als voorwaarde](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="eac14-325">Eenvoudige instellingen versus geavanceerde instellingen</span><span class="sxs-lookup"><span data-stu-id="eac14-325">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="eac14-326">Wanneer u een DLP-beleid maakt, kiest u tussen eenvoudige of geavanceerde instellingen:</span><span class="sxs-lookup"><span data-stu-id="eac14-326">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="eac14-327">**Met eenvoudige** instellingen kunt u eenvoudig het meest voorkomende type DLP-beleid maken zonder de regeleditor te gebruiken om regels te maken of te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="eac14-327">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="eac14-328">**Geavanceerde instellingen** gebruiken de regeleditor om u volledige controle te geven over elke instelling voor uw DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-328">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="eac14-329">Maak u geen zorgen, onder de omslagen werken eenvoudige instellingen en geavanceerde instellingen precies hetzelfde door regels te afdwingen die bestaan uit voorwaarden en acties. Alleen met eenvoudige instellingen ziet u de regeleditor niet.</span><span class="sxs-lookup"><span data-stu-id="eac14-329">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions—only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="eac14-330">Dit is een snelle manier om een DLP-beleid te maken.</span><span class="sxs-lookup"><span data-stu-id="eac14-330">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="eac14-331">Eenvoudige instellingen</span><span class="sxs-lookup"><span data-stu-id="eac14-331">Simple settings</span></span>

<span data-ttu-id="eac14-332">Het meest voorkomende DLP-scenario is het maken van een beleid om te helpen voorkomen dat inhoud met gevoelige informatie wordt gedeeld met personen buiten uw organisatie, en een automatische herstelactie uit te voeren, zoals het beperken van wie toegang heeft tot de inhoud, het verzenden van meldingen van eindgebruikers of beheerders en het controleren van de gebeurtenis voor later onderzoek.</span><span class="sxs-lookup"><span data-stu-id="eac14-332">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remediating action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="eac14-333">Personen gebruiken DLP om onbedoelde openbaarmaking van gevoelige informatie te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="eac14-333">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="eac14-334">Als u het bereiken van dit doel wilt vereenvoudigen, kunt u bij het maken van een DLP-beleid eenvoudige **instellingen gebruiken kiezen.**</span><span class="sxs-lookup"><span data-stu-id="eac14-334">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="eac14-335">Deze instellingen bieden alles wat u nodig hebt om het meest voorkomende DLP-beleid te implementeren, zonder dat u naar de regeleditor hoeft te gaan.</span><span class="sxs-lookup"><span data-stu-id="eac14-335">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![DLP-opties voor eenvoudige en geavanceerde instellingen](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="eac14-337">Geavanceerde instellingen</span><span class="sxs-lookup"><span data-stu-id="eac14-337">Advanced settings</span></span>

<span data-ttu-id="eac14-338">Als u meer aangepaste DLP-beleidsregels wilt maken, kunt u **Geavanceerde instellingen gebruiken kiezen.**</span><span class="sxs-lookup"><span data-stu-id="eac14-338">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="eac14-339">De geavanceerde instellingen presenteren u met de regeleditor, waar u volledige controle hebt over alle mogelijke opties, inclusief het aantal exemplaren en de nauwkeurigheid (betrouwbaarheidsniveau) voor elke regel.</span><span class="sxs-lookup"><span data-stu-id="eac14-339">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="eac14-340">Als u snel naar een sectie wilt gaan, klikt u op een item in de bovenste navigatie van de regeleditor om naar die sectie hieronder te gaan.</span><span class="sxs-lookup"><span data-stu-id="eac14-340">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![Bovenste navigatiemenu van DLP-regeleditor](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="eac14-342">DLP-beleidsjablonen</span><span class="sxs-lookup"><span data-stu-id="eac14-342">DLP policy templates</span></span>

<span data-ttu-id="eac14-343">De eerste stap bij het maken van een DLP-beleid is het kiezen van welke informatie u wilt beveiligen.</span><span class="sxs-lookup"><span data-stu-id="eac14-343">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="eac14-344">Door te beginnen met een DLP-sjabloon, kunt u het werk van het maken van een nieuwe set regels vanaf het begin opslaan en uitzoeken welke typen gegevens standaard moeten worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="eac14-344">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="eac14-345">Vervolgens kunt u deze vereisten toevoegen aan of wijzigen om de regel aan te passen aan de specifieke vereisten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-345">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="eac14-346">Een vooraf geconfigureerde DLP-beleidssjabloon kan u helpen specifieke typen gevoelige informatie te detecteren, zoals HIPAA-gegevens, PCI-DSS-gegevens, Gramm-Leach-Bliley Act-gegevens of zelfs locale-specifieke persoonsgegevens (P.I.).</span><span class="sxs-lookup"><span data-stu-id="eac14-346">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="eac14-347">Om het u gemakkelijk te maken om veelvoorkomende typen gevoelige informatie te vinden en te beveiligen, bevatten de beleidssjablonen in Microsoft 365 al de meest voorkomende typen gevoelige informatie die nodig zijn om aan de slag te gaan.</span><span class="sxs-lookup"><span data-stu-id="eac14-347">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Microsoft 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![Lijst met sjablonen voor preventiebeleid voor gegevensverlies met de focus op sjabloon voor de Amerikaanse Patriot Act](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="eac14-349">Uw organisatie heeft mogelijk ook eigen specifieke vereisten, in dat geval kunt u een volledig DLP-beleid maken door de optie Aangepast **beleid te** kiezen.</span><span class="sxs-lookup"><span data-stu-id="eac14-349">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="eac14-350">Een aangepast beleid is leeg en bevat geen vooraf gemaakte regels.</span><span class="sxs-lookup"><span data-stu-id="eac14-350">A custom policy is empty and contains no premade rules.</span></span> 
  
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
  
## <a name="dlp-reports"></a><span data-ttu-id="eac14-351">DLP-rapporten</span><span class="sxs-lookup"><span data-stu-id="eac14-351">DLP reports</span></span>

<span data-ttu-id="eac14-352">Nadat u uw DLP-beleid hebt gemaakt en in- of uit gebruik hebt gemaakt, wilt u controleren of ze werken zoals u had bedoeld en u helpen om aan de vereisten te voldoen.</span><span class="sxs-lookup"><span data-stu-id="eac14-352">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="eac14-353">Met DLP-rapporten kunt u snel het aantal DLP-beleid- en regelwedstrijden in de tijd bekijken en het aantal onwaar-positieven en overschrijven.</span><span class="sxs-lookup"><span data-stu-id="eac14-353">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="eac14-354">Voor elk rapport kunt u deze overeenkomsten filteren op locatie, tijdskader en zelfs beperken tot een specifiek beleid, regel of actie.</span><span class="sxs-lookup"><span data-stu-id="eac14-354">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="eac14-355">Met de DLP-rapporten kunt u bedrijfsinzichten krijgen en:</span><span class="sxs-lookup"><span data-stu-id="eac14-355">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="eac14-356">Focus op specifieke tijdsperiodes en begrijp de redenen voor pieken en trends.</span><span class="sxs-lookup"><span data-stu-id="eac14-356">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="eac14-357">Ontdek bedrijfsprocessen die in strijd zijn met het compliancebeleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-357">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="eac14-358">Begrijp de zakelijke impact van het DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-358">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="eac14-359">Daarnaast kunt u de DLP-rapporten gebruiken om uw DLP-beleid aan te passen terwijl u ze uit runt.</span><span class="sxs-lookup"><span data-stu-id="eac14-359">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![Rapportendashboard in beveiligings- en compliancecentrum](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="eac14-361">Hoe DLP-beleid werkt</span><span class="sxs-lookup"><span data-stu-id="eac14-361">How DLP policies work</span></span>

<span data-ttu-id="eac14-362">DLP detecteert gevoelige informatie met behulp van diepe inhoudsanalyse (niet alleen een eenvoudige tekstscan).</span><span class="sxs-lookup"><span data-stu-id="eac14-362">DLP detects sensitive information by using deep content analysis (not just a simple text scan).</span></span> <span data-ttu-id="eac14-363">In deze uitgebreide inhoudsanalyse worden trefwoorden, woordenlijsten, de evaluatie van reguliere expressies, interne functies en andere methoden gebruikt om inhoud te detecteren die overeenkomt met uw DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-363">This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies.</span></span> <span data-ttu-id="eac14-364">Mogelijk wordt slechts een klein percentage van uw gegevens als gevoelig beschouwd.</span><span class="sxs-lookup"><span data-stu-id="eac14-364">Potentially only a small percentage of your data is considered sensitive.</span></span> <span data-ttu-id="eac14-365">Een DLP-beleid kan alleen die gegevens identificeren, controleren en automatisch beveiligen, zonder dat dit gevolgen heeft voor personen die met de rest van uw inhoud werken.</span><span class="sxs-lookup"><span data-stu-id="eac14-365">A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="eac14-366">Beleidsregels worden gesynchroniseerd</span><span class="sxs-lookup"><span data-stu-id="eac14-366">Policies are synced</span></span>

<span data-ttu-id="eac14-367">Nadat u een DLP-beleid hebt in het Beveiligings compliancecentrum, wordt het opgeslagen in een centrale beleidsopslag en vervolgens gesynchroniseerd met de verschillende &amp; inhoudsbronnen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="eac14-367">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="eac14-368">Exchange Online en van daar naar webversie van Outlook en Outlook.</span><span class="sxs-lookup"><span data-stu-id="eac14-368">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
    
- <span data-ttu-id="eac14-369">OneDrive voor Bedrijven sites.</span><span class="sxs-lookup"><span data-stu-id="eac14-369">OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="eac14-370">SharePoint Onlinesites.</span><span class="sxs-lookup"><span data-stu-id="eac14-370">SharePoint Online sites.</span></span>
    
- <span data-ttu-id="eac14-371">Office bureaubladprogramma's (Excel, PowerPoint en Word).</span><span class="sxs-lookup"><span data-stu-id="eac14-371">Office desktop programs (Excel, PowerPoint, and Word).</span></span>

- <span data-ttu-id="eac14-372">Microsoft Teams kanalen en chatberichten.</span><span class="sxs-lookup"><span data-stu-id="eac14-372">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="eac14-373">Nadat het beleid is gesynchroniseerd met de juiste locaties, wordt gestart met het evalueren van inhoud en het afdwingen van acties.</span><span class="sxs-lookup"><span data-stu-id="eac14-373">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="eac14-374">Beleidsevaluatie op OneDrive voor Bedrijven en SharePoint onlinesites</span><span class="sxs-lookup"><span data-stu-id="eac14-374">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="eac14-375">Op al uw SharePoint Online-sites en OneDrive voor Bedrijven-sites veranderen documenten voortdurend. Ze worden voortdurend gemaakt, bewerkt, gedeeld, en ga zo maar door.</span><span class="sxs-lookup"><span data-stu-id="eac14-375">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="eac14-376">Dit betekent dat documenten op elk moment kunnen conflicteren met een DLP-beleid of in overeenstemming kunnen zijn met een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-376">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="eac14-377">Een persoon kan bijvoorbeeld een document uploaden dat geen gevoelige informatie bevat naar zijn of haar teamsite, maar later kan een andere persoon hetzelfde document bewerken en er gevoelige informatie aan toevoegen.</span><span class="sxs-lookup"><span data-stu-id="eac14-377">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="eac14-378">Daarom controleren DLP-beleidsregels documenten regelmatig op beleidswedstrijden op de achtergrond.</span><span class="sxs-lookup"><span data-stu-id="eac14-378">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="eac14-379">U kunt dit zien als een asynchrone beleidsevaluatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-379">You can think of this as asynchronous policy evaluation.</span></span>
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a><span data-ttu-id="eac14-380">Hoe het werkt</span><span class="sxs-lookup"><span data-stu-id="eac14-380">How it works</span></span>
 
<span data-ttu-id="eac14-381">Wanneer personen documenten op hun sites toevoegen of wijzigen, scant de zoekmachine de inhoud, zodat u er later naar kunt zoeken.</span><span class="sxs-lookup"><span data-stu-id="eac14-381">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="eac14-382">Terwijl dit gebeurt, wordt de inhoud ook gescand op gevoelige informatie en wordt gecontroleerd of deze wordt gedeeld.</span><span class="sxs-lookup"><span data-stu-id="eac14-382">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="eac14-383">Alle gevoelige informatie die wordt gevonden, wordt veilig opgeslagen in de zoekindex, zodat alleen het complianceteam er toegang toe heeft, maar geen gewone gebruikers.</span><span class="sxs-lookup"><span data-stu-id="eac14-383">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="eac14-384">Elk DLP-beleid dat u hebt ingeschakeld, wordt uitgevoerd op de achtergrond (asynchroon), vaak zoeken naar inhoud die overeenkomt met een beleid en acties toepassen om het te beschermen tegen onbedoelde lekken.</span><span class="sxs-lookup"><span data-stu-id="eac14-384">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![Diagram waarin wordt getoond hoe inhoud asynchroon wordt geëvalueerd in het DLP-beleid](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording -->
<span data-ttu-id="eac14-386">Ten slotte kunnen documenten conflicteren met een DLP-beleid, maar ze kunnen ook voldoen aan een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-386">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy.</span></span> <span data-ttu-id="eac14-387">Als een persoon bijvoorbeeld creditcardnummers toevoegt aan een document, kan een DLP-beleid ervoor zorgen dat de toegang tot het document automatisch wordt geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="eac14-387">For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically.</span></span> <span data-ttu-id="eac14-388">Maar als de persoon de gevoelige informatie later verwijdert, wordt de actie (in dit geval blokkeren) automatisch ongedaan gemaakt wanneer het document de volgende keer wordt geëvalueerd op basis van het beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-388">But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="eac14-389">DLP evalueert alle inhoud die kan worden geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="eac14-389">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="eac14-390">Zie Standaard verkende [bestandsextensies en geparseerde bestandstypen in SharePoint Server voor meer informatie over welke bestandstypen standaard worden verkend.](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)</span><span class="sxs-lookup"><span data-stu-id="eac14-390">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>

> [!NOTE]
> <span data-ttu-id="eac14-391">Als u wilt voorkomen dat documenten worden gedeeld voordat DLP-beleid de mogelijkheid had om ze te analyseren, kan het delen van nieuwe bestanden in SharePoint worden geblokkeerd totdat de inhoud is geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="eac14-391">In order to prevent documents from being shared before DLP policies had the opportunity to analyze them, sharing of new files in SharePoint can be blocked until its content has been indexed.</span></span> <span data-ttu-id="eac14-392">Zie Nieuwe [bestanden standaard markeren als gevoelig voor](/sharepoint/sensitive-by-default) gedetailleerde informatie.</span><span class="sxs-lookup"><span data-stu-id="eac14-392">See, [Mark new files as sensitive by default](/sharepoint/sensitive-by-default) for detailed information.</span></span> 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="eac14-393">Beleidsevaluatie in Exchange Online, Outlook en webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="eac14-393">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="eac14-394">Wanneer u een DLP-beleid maakt dat Exchange Online als locatie bevat, wordt het beleid gesynchroniseerd van het Office 365 Security Compliance Center naar Exchange Online en vervolgens van Exchange Online naar webversie van Outlook en &amp; Outlook.</span><span class="sxs-lookup"><span data-stu-id="eac14-394">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="eac14-395">Wanneer een bericht wordt samengesteld in Outlook, kan de gebruiker beleidstips zien terwijl de inhoud die wordt gemaakt, wordt geëvalueerd op basis van DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-395">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="eac14-396">Nadat een bericht is verzonden, wordt dit geëvalueerd op basis van DLP-beleid als een normaal onderdeel van de e-mailstroom, samen met Exchange regels voor e-mailstroom (ook wel transportregels genoemd) en DLP-beleid dat is gemaakt in het Exchange-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="eac14-396">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="eac14-397">DLP-beleid scant zowel het bericht als eventuele bijlagen.</span><span class="sxs-lookup"><span data-stu-id="eac14-397">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="eac14-398">Beleidsevaluatie in de Office bureaubladprogramma's</span><span class="sxs-lookup"><span data-stu-id="eac14-398">Policy evaluation in the Office desktop programs</span></span>

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
<span data-ttu-id="eac14-399">Excel, PowerPoint en Word bevatten dezelfde mogelijkheid om gevoelige informatie te identificeren en DLP-beleid toe te passen als SharePoint Online en OneDrive voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="eac14-399">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="eac14-400">Deze Office programma's synchroniseren hun DLP-beleid rechtstreeks vanuit de centrale beleidsopslag en evalueren vervolgens continu de inhoud tegen het DLP-beleid wanneer personen werken met documenten die zijn geopend vanaf een site die is opgenomen in een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-400">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="eac14-401">DLP-beleidsevaluatie in Office is ontworpen om de prestaties van de programma's of de productiviteit van personen die aan inhoud werken, niet te beïnvloeden.</span><span class="sxs-lookup"><span data-stu-id="eac14-401">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="eac14-402">Als ze aan een groot document werken of de computer van de gebruiker bezet is, kan het enkele seconden duren voordat een beleidstip wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="eac14-402">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="eac14-403">Beleidsevaluatie in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eac14-403">Policy evaluation in Microsoft Teams</span></span>
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

<span data-ttu-id="eac14-404">Wanneer u een DLP-beleid maakt dat Microsoft Teams als locatie bevat, wordt het beleid gesynchroniseerd vanuit het Office 365 Security Compliance Center naar gebruikersaccounts en Microsoft Teams kanalen en &amp; chatberichten.</span><span class="sxs-lookup"><span data-stu-id="eac14-404">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="eac14-405">Afhankelijk van hoe DLP-beleid is geconfigureerd, kan het bericht worden geblokkeerd of ingetrokken wanneer iemand gevoelige informatie probeert te delen in een Microsoft Teams chat- of kanaalbericht.</span><span class="sxs-lookup"><span data-stu-id="eac14-405">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="eac14-406">En documenten die gevoelige informatie bevatten en die worden gedeeld met gasten (externe gebruikers) worden niet geopend voor deze gebruikers.</span><span class="sxs-lookup"><span data-stu-id="eac14-406">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="eac14-407">Zie Preventie en preventie van [gegevensverlies](dlp-microsoft-teams.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eac14-407">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="eac14-408">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="eac14-408">Permissions</span></span>

<span data-ttu-id="eac14-409">Globale beheerders, beveiligingsbeheerders en compliancebeheerders hebben standaard toegang tot het maken en toepassen van een DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="eac14-409">By default, Global admins, Security admins, and Compliance admins will have access to create and apply a DLP policy.</span></span> <span data-ttu-id="eac14-410">Andere leden van uw complianceteam die DLP-beleidsregels maken, hebben machtigingen nodig voor het Beveiligings &amp; compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="eac14-410">Other Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="eac14-411">Uw tenantbeheerder heeft standaard toegang tot deze locatie en kan compliancemedewerkers en andere personen toegang geven tot het Beveiligings compliancecentrum, zonder dat ze alle machtigingen van een &amp; tenantbeheerder hebben. U wordt aangeraden het volgende te doen:</span><span class="sxs-lookup"><span data-stu-id="eac14-411">By default, your Tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a Tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="eac14-412">Maak een groep in Microsoft 365 en voeg compliance officers toe aan deze groep.</span><span class="sxs-lookup"><span data-stu-id="eac14-412">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="eac14-413">Maak een rollengroep op de **pagina Machtigingen** van het Beveiligings &amp; compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="eac14-413">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="eac14-414">Terwijl u de rollengroep maakt, gebruikt u **de** sectie Rollen kiezen om de volgende rol toe te voegen aan de rollengroep: **DLP Compliance Management.**</span><span class="sxs-lookup"><span data-stu-id="eac14-414">While creating the role group, use the **Choose Roles** section to add the following role to the Role Group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="eac14-415">Gebruik de **sectie Leden kiezen** om de groep Microsoft 365 die u eerder hebt gemaakt, toe te voegen aan de rollengroep.</span><span class="sxs-lookup"><span data-stu-id="eac14-415">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="eac14-416">U kunt ook een rollengroep maken met alleen-weergeven-bevoegdheden voor het DLP-beleid en DLP-rapporten door de functie **Alleen-weergeven DLP-compliancebeheer toe te** staan.</span><span class="sxs-lookup"><span data-stu-id="eac14-416">You can also create a role group with view-only privileges to the DLP policies and DLP reports by granting the **View-Only DLP Compliance Management** role.</span></span>

<span data-ttu-id="eac14-417">Zie Gebruikers toegang geven tot het Office 365 [Compliance Center voor meer informatie.](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="eac14-417">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="eac14-418">Deze machtigingen zijn alleen vereist om een DLP-beleid te maken en toe te passen.</span><span class="sxs-lookup"><span data-stu-id="eac14-418">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="eac14-419">Beleidshandhaving vereist geen toegang tot de inhoud.</span><span class="sxs-lookup"><span data-stu-id="eac14-419">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="eac14-420">De DLP-cmdlets zoeken</span><span class="sxs-lookup"><span data-stu-id="eac14-420">Find the DLP cmdlets</span></span>

<span data-ttu-id="eac14-421">Als u de meeste cmdlets wilt gebruiken voor het Beveiligings &amp; compliancecentrum, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="eac14-421">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. <span data-ttu-id="eac14-422">[Verbinding maken naar de Office 365 Beveiliging &amp; Compliancecentrum met behulp van externe PowerShell.](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="eac14-422">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="eac14-423">Gebruik een van deze [policy-and-compliance-dlp-cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span><span class="sxs-lookup"><span data-stu-id="eac14-423">Use any of these [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span></span>
    
<span data-ttu-id="eac14-424">In DLP-rapporten moeten echter gegevens uit verschillende Microsoft 365 worden verzameld, inclusief Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="eac14-424">However, DLP reports need pull data from across Microsoft 365, including Exchange Online.</span></span> <span data-ttu-id="eac14-425">Daarom zijn de **cmdlets voor de DLP-rapporten beschikbaar in Exchange Online Powershell, niet in Security &amp; Compliance Center Powershell.**</span><span class="sxs-lookup"><span data-stu-id="eac14-425">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="eac14-426">Als u de cmdlets voor de DLP-rapporten wilt gebruiken, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="eac14-426">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. <span data-ttu-id="eac14-427">[Maak verbinding met Exchange Online via externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="eac14-427">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="eac14-428">Gebruik een van deze cmdlets voor de DLP-rapporten:</span><span class="sxs-lookup"><span data-stu-id="eac14-428">Use any of these cmdlets for the DLP reports:</span></span>
    
    - [<span data-ttu-id="eac14-429">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="eac14-429">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [<span data-ttu-id="eac14-430">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="eac14-430">Get-DlpDetailReport</span></span>](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a><span data-ttu-id="eac14-431">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="eac14-431">More information</span></span>

- [<span data-ttu-id="eac14-432">Een DLP-beleid maken vanuit een sjabloon</span><span class="sxs-lookup"><span data-stu-id="eac14-432">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="eac14-433">Meldingen verzenden en beleidstips voor DLP-beleid tonen</span><span class="sxs-lookup"><span data-stu-id="eac14-433">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="eac14-434">Een DLP-beleid maken om documenten te beveiligen met FCI of andere eigenschappen</span><span class="sxs-lookup"><span data-stu-id="eac14-434">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="eac14-435">Wat zijn de DLP-beleidssjablonen?</span><span class="sxs-lookup"><span data-stu-id="eac14-435">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="eac14-436">Definities van entiteiten van het type vertrouwelijke gegevens</span><span class="sxs-lookup"><span data-stu-id="eac14-436">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="eac14-437">Doel van de DLP-functies</span><span class="sxs-lookup"><span data-stu-id="eac14-437">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="eac14-438">Een aangepast type gevoelige informatie maken</span><span class="sxs-lookup"><span data-stu-id="eac14-438">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
