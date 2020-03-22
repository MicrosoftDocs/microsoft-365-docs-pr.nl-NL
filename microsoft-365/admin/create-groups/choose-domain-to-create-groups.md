---
title: Het domein kiezen dat u wilt gebruiken voor het maken van Office 365-groepen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Lees het domein dat u wilt gebruiken bij het maken van Office 365-groepen door het beleid voor e-mailadressen te configureren met PowerShell. '
ms.openlocfilehash: 8bca0e3c33d5cb523fc075d1d2d5b04b6506b256
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894643"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a><span data-ttu-id="d872a-103">Het domein kiezen dat u wilt gebruiken voor het maken van Office 365-groepen</span><span class="sxs-lookup"><span data-stu-id="d872a-103">Choose the domain to use when creating Office 365 Groups</span></span>

 <span data-ttu-id="d872a-p101">Sommige organisaties gebruiken afzonderlijke e-maildomeinen om verschillende onderdelen van het bedrijf te segmenteren. U kunt opgeven welk domein moet worden gebruikt als uw gebruikers Office 365-groepen maken.</span><span class="sxs-lookup"><span data-stu-id="d872a-p101">Some organizations use separate email domains to segment different parts of their businesses. You can specify which domain should be used when your users create Office 365 groups.</span></span>
  
<span data-ttu-id="d872a-106">Als uw organisatie vereist dat gebruikers hun groepen maken in andere domeinen dan het standaard geaccepteerde domein van uw bedrijf, kunt u dit toestaan door met PowerShell e-mailadresbeleidsregels (EAP's) te configureren.</span><span class="sxs-lookup"><span data-stu-id="d872a-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="d872a-p102">U kunt de PowerShell-cmdlets pas uitvoeren nadat u een module hebt gedownload en geïnstalleerd die het mogelijk maakt om met uw Office 365-organisatie te communiceren. Zie [Verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881)</span><span class="sxs-lookup"><span data-stu-id="d872a-p102">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your Office 365 organization. Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="d872a-109">Voorbeelden van scenario's</span><span class="sxs-lookup"><span data-stu-id="d872a-109">Example scenarios</span></span>

<span data-ttu-id="d872a-110">Stel dat Contoso.com het primaire domein van uw bedrijf is.</span><span class="sxs-lookup"><span data-stu-id="d872a-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="d872a-111">Het standaard geaccepteerde domein van uw organisatie is echter service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d872a-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="d872a-112">Dit betekent dat groepen worden gemaakt in service.contoso.com (bijvoorbeeld jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="d872a-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="d872a-113">Stel dat er ook subdomeinen zijn geconfigureerd in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d872a-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="d872a-114">U wilt ook dat groepen in deze domeinen worden gemaakt:</span><span class="sxs-lookup"><span data-stu-id="d872a-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="d872a-115">students.contoso.com voor studenten</span><span class="sxs-lookup"><span data-stu-id="d872a-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="d872a-116">faculty.contoso.com voor faculteitsleden</span><span class="sxs-lookup"><span data-stu-id="d872a-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="d872a-117">In de volgende twee scenario's wordt uitgelegd hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="d872a-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d872a-118">Als u meerdere EAP's hebt, worden deze in volgorde van prioriteit geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="d872a-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="d872a-119">De waarde 1 betekent de hoogste prioriteit.</span><span class="sxs-lookup"><span data-stu-id="d872a-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="d872a-120">Zodra een EAP overeenkomt, wordt er geen verdere EAP geëvalueerd en adressen die op de groep worden gestempeld, zijn volgens het overeenkomende EAP.</span><span class="sxs-lookup"><span data-stu-id="d872a-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="d872a-121">> Als er geen EAP's overeenkomen met de opgegeven criteria, wordt de groep ingericht in het standaard geaccepteerde domein van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="d872a-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="d872a-122">Bekijk [Geaccepteerd domeinen beheren in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) voor meer informatie over het toevoegen van een geaccepteerd domein.</span><span class="sxs-lookup"><span data-stu-id="d872a-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="d872a-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="d872a-123">Scenario 1</span></span>

<span data-ttu-id="d872a-124">In het volgende voorbeeld ziet u hoe u alle Office 365-groepen in uw organisatie inricht in het domein groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d872a-124">The following example shows you how to provision all Office 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="d872a-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="d872a-125">Scenario 2</span></span>

<span data-ttu-id="d872a-126">Stel dat u wilt bepalen in welke subdomeinen Office 365-groepen worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d872a-126">Let's say you want to control what sub-domains Office 365 groups are created in.</span></span> <span data-ttu-id="d872a-127">U wilt dat:</span><span class="sxs-lookup"><span data-stu-id="d872a-127">You want:</span></span>
  
- <span data-ttu-id="d872a-128">Groepen die zijn gemaakt door studenten (gebruikers die **afdeling** hebben ingesteld op **studenten)** in het students.groups.contoso.com domein.</span><span class="sxs-lookup"><span data-stu-id="d872a-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="d872a-129">Gebruik deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="d872a-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="d872a-130">Groepen die zijn gemaakt door faculteitsleden (gebruikers die **de afdeling** hebben ingesteld op faculteit **of e-mailadres faculty.contoso.com)**) in het domein faculty.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d872a-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="d872a-131">Gebruik deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="d872a-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="d872a-132">Alle andere gebruikers terechtkomen in het domein groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d872a-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="d872a-133">Gebruik deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="d872a-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="d872a-134">E-mailadresbeleidsregels wijzigen</span><span class="sxs-lookup"><span data-stu-id="d872a-134">Change email address policies</span></span>

<span data-ttu-id="d872a-135">Gebruik de cmdlet Set-EmailAddressPolicy als u de prioriteit of e-mailadressjablonen voor een bestaand EAP wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d872a-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="d872a-136">Het wijzigen van een EAP heeft geen invloed op de groepen die al zijn ingericht.</span><span class="sxs-lookup"><span data-stu-id="d872a-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="d872a-137">E-mailadresbeleidsregels verwijderen</span><span class="sxs-lookup"><span data-stu-id="d872a-137">Delete email address policies</span></span>

<span data-ttu-id="d872a-138">Gebruik de cmdlet Remove-EmailAddressPolicy om een EAP te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d872a-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="d872a-139">Het wijzigen van een EAP heeft geen invloed op de groepen die al zijn ingericht.</span><span class="sxs-lookup"><span data-stu-id="d872a-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="d872a-140">Hybride vereisten</span><span class="sxs-lookup"><span data-stu-id="d872a-140">Hybrid requirements</span></span>

<span data-ttu-id="d872a-141">Als uw organisatie is geconfigureerd in een hybride scenario, raadpleeg dan [Office 365-groepen configureren met een hybride on-premises implementatie van Exchange](https://go.microsoft.com/fwlink/p/?LinkId=785430) om ervoor te zorgen dat uw organisatie voldoet aan de vereisten voor het maken van Office 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="d872a-141">If your organization is configured in a hybrid scenario, check out [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Office 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="d872a-142">Aanvullende informatie over het gebruik van beleidsgroepen voor e-mailadressen:</span><span class="sxs-lookup"><span data-stu-id="d872a-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="d872a-143">Er zijn nog een paar dingen die u moet weten:</span><span class="sxs-lookup"><span data-stu-id="d872a-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="d872a-144">De snelheid waarmee groepen worden gemaakt, hangt af van het aantal EAP's dat in uw organisatie is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="d872a-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="d872a-145">Beheerders en gebruikers kunnen ook domeinen wijzigen wanneer ze groepen maken.</span><span class="sxs-lookup"><span data-stu-id="d872a-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="d872a-146">De groep gebruikers wordt bepaald met standaardquery's (Gebruikerseigenschappen), die al beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="d872a-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="d872a-147">Controleer [Filterbare eigenschappen voor de parameter -RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918) voor ondersteunde filterbare eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="d872a-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="d872a-148">Als u geen EAP's voor groepen configureert, wordt het standaard geaccepteerd domein voor het maken van groepen geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="d872a-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="d872a-149">Als u een geaccepteerd domein verwijdert, moet u eerst de EAP's bijwerken, anders heeft dit invloed op de inrichting van de groep.</span><span class="sxs-lookup"><span data-stu-id="d872a-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="d872a-150">Er kunnen maximaal 100 e-mailadresbeleidsregel voor een organisatie worden geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="d872a-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="d872a-151">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d872a-151">Related articles</span></span>

[<span data-ttu-id="d872a-152">Een Office 365-groep maken in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="d872a-152">Create an Office 365 group in the admin center</span></span>](create-groups.md)
