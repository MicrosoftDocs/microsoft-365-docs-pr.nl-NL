---
title: Kies het domein dat u wilt gebruiken bij het maken van Microsoft 365-groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Informatie over het domein dat u wilt gebruiken bij het maken van Microsoft 365-groepen door e-mailadresbeleid te configureren met PowerShell.
ms.openlocfilehash: 4908d5bd58ca6d0fbb50151983ddb459f0732284
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904682"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="539be-103">Kies het domein dat u wilt gebruiken bij het maken van Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="539be-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="539be-104">Sommige organisaties gebruiken afzonderlijke e-maildomeinen om verschillende onderdelen van het bedrijf te segmenteren.</span><span class="sxs-lookup"><span data-stu-id="539be-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="539be-105">U kunt opgeven welk domein moet worden gebruikt wanneer uw gebruikers Microsoft 365-groepen maken.</span><span class="sxs-lookup"><span data-stu-id="539be-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="539be-106">Als uw organisatie vereist dat gebruikers hun groepen maken in andere domeinen dan het standaard geaccepteerde domein van uw bedrijf, kunt u dit toestaan door met PowerShell e-mailadresbeleidsregels (EAP's) te configureren.</span><span class="sxs-lookup"><span data-stu-id="539be-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="539be-107">Voordat u de PowerShell-cmdlets kunt uitvoeren, downloadt en installeert u een module om met uw organisatie te praten.</span><span class="sxs-lookup"><span data-stu-id="539be-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="539be-108">Zie [Verbinding maken met Exchange Online via externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="539be-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="539be-109">Voorbeelden van scenario's</span><span class="sxs-lookup"><span data-stu-id="539be-109">Example scenarios</span></span>

<span data-ttu-id="539be-110">Stel dat Contoso.com het primaire domein van uw bedrijf is.</span><span class="sxs-lookup"><span data-stu-id="539be-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="539be-111">Het standaard geaccepteerde domein van uw organisatie is echter service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="539be-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="539be-112">Dit betekent dat groepen worden gemaakt in service.contoso.com (bijvoorbeeld jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="539be-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="539be-113">Stel dat er ook subdomeinen zijn geconfigureerd in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="539be-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="539be-114">U wilt ook groepen maken in deze domeinen:</span><span class="sxs-lookup"><span data-stu-id="539be-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="539be-115">students.contoso.com voor studenten</span><span class="sxs-lookup"><span data-stu-id="539be-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="539be-116">faculty.contoso.com voor faculteitsleden</span><span class="sxs-lookup"><span data-stu-id="539be-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="539be-117">In de volgende twee scenario's wordt uitgelegd hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="539be-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="539be-118">Als u meerdere EAP's hebt, worden deze in volgorde van prioriteit geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="539be-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="539be-119">De waarde 1 betekent de hoogste prioriteit.</span><span class="sxs-lookup"><span data-stu-id="539be-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="539be-120">Wanneer een EAP overeenkomt, wordt er geen EAP meer geëvalueerd en worden adressen die op de groep worden gestempeld, volgens het overeenkomende EAP geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="539be-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="539be-121">> Als er geen EPP's voldoen aan de opgegeven criteria, wordt de groep ingericht in het standaard geaccepteerde domein van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="539be-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="539be-122">Bekijk [Geaccepteerd domeinen beheren in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) voor meer informatie over het toevoegen van een geaccepteerd domein.</span><span class="sxs-lookup"><span data-stu-id="539be-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="539be-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="539be-123">Scenario 1</span></span>

<span data-ttu-id="539be-124">In het volgende voorbeeld ziet u hoe u alle Microsoft 365-groepen in uw organisatie kunt inrichten in groups.contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="539be-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="539be-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="539be-125">Scenario 2</span></span>

<span data-ttu-id="539be-126">Stel dat u wilt bepalen in welke subdomeinen Microsoft 365-groepen worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="539be-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="539be-127">U wilt dat:</span><span class="sxs-lookup"><span data-stu-id="539be-127">You want:</span></span>
  
- <span data-ttu-id="539be-128">Groepen die zijn gemaakt door leerlingen/studenten (gebruikers die **afdeling** hebben ingesteld op **Studenten)** in het students.groups.contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="539be-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="539be-129">Gebruik deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="539be-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="539be-130">Groepen die zijn gemaakt door  faculteitsleden (gebruikers die afdeling hebben ingesteld op Faculteit of e-mailadres bevat **faculty.contoso.com)** in het faculty.groups.contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="539be-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="539be-131">Gebruik deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="539be-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="539be-132">Groepen die door iemand anders zijn gemaakt, worden gemaakt in het groups.contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="539be-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="539be-133">Gebruik deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="539be-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="539be-134">E-mailadresbeleidsregels wijzigen</span><span class="sxs-lookup"><span data-stu-id="539be-134">Change email address policies</span></span>

<span data-ttu-id="539be-135">Gebruik de cmdlet Set-EmailAddressPolicy als u de prioriteit of e-mailadressjablonen voor een bestaand EAP wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="539be-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="539be-136">Het wijzigen van een EAP heeft geen invloed op de groepen die al zijn ingericht.</span><span class="sxs-lookup"><span data-stu-id="539be-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="539be-137">E-mailadresbeleidsregels verwijderen</span><span class="sxs-lookup"><span data-stu-id="539be-137">Delete email address policies</span></span>

<span data-ttu-id="539be-138">Gebruik de cmdlet Remove-EmailAddressPolicy om een EAP te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="539be-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="539be-139">Het wijzigen van een EAP heeft geen invloed op de groepen die al zijn ingericht.</span><span class="sxs-lookup"><span data-stu-id="539be-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="539be-140">Hybride vereisten</span><span class="sxs-lookup"><span data-stu-id="539be-140">Hybrid requirements</span></span>

<span data-ttu-id="539be-141">Als uw organisatie is geconfigureerd in een hybride scenario, raadpleegt u [Microsoft 365-groepen](/exchange/hybrid-deployment/set-up-microsoft-365-groups) configureren met on-premises Exchange-hybride om ervoor te zorgen dat uw organisatie voldoet aan de vereisten voor het maken van Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="539be-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="539be-142">Aanvullende informatie over het gebruik van e-mailadresbeleidsgroepen:</span><span class="sxs-lookup"><span data-stu-id="539be-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="539be-143">Er zijn nog een paar dingen die u moet weten:</span><span class="sxs-lookup"><span data-stu-id="539be-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="539be-144">De snelheid waarmee groepen worden gemaakt, hangt af van het aantal EAP's dat in uw organisatie is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="539be-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="539be-145">Beheerders en gebruikers kunnen ook domeinen wijzigen wanneer ze groepen maken.</span><span class="sxs-lookup"><span data-stu-id="539be-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="539be-146">De groep gebruikers wordt bepaald met standaardquery's (Gebruikerseigenschappen), die al beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="539be-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="539be-147">Bekijk [Filterbare eigenschappen voor de parameter -RecipientFilter](/powershell/exchange/recipientfilter-properties) voor ondersteunde filterbare eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="539be-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="539be-148">Als u geen EAP's voor groepen configureert, wordt het standaard geaccepteerd domein voor het maken van groepen geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="539be-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="539be-149">Als u een geaccepteerd domein verwijdert, moet u eerst de EAP's bijwerken, anders heeft dit invloed op de inrichting van de groep.</span><span class="sxs-lookup"><span data-stu-id="539be-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="539be-150">Er kunnen maximaal 100 e-mailadresbeleidsregel voor een organisatie worden geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="539be-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="539be-151">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="539be-151">Related articles</span></span>

[<span data-ttu-id="539be-152">Planning van samenwerkingsbeheer stap voor stap</span><span class="sxs-lookup"><span data-stu-id="539be-152">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="539be-153">Uw samenwerkingsbeheerplan maken</span><span class="sxs-lookup"><span data-stu-id="539be-153">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="539be-154">Een Microsoft 365-groep maken in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="539be-154">Create an Microsoft 365 group in the admin center</span></span>](../admin/create-groups/create-groups.md)