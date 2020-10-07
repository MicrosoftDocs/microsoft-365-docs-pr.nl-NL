---
title: Het domein kiezen dat u wilt gebruiken voor het maken van Microsoft 365-groepen
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
description: Leer het domein kiezen dat u wilt gebruiken voor het maken van Microsoft 365-groepen door e-mailadres beleidsregels te configureren met PowerShell.
ms.openlocfilehash: bb6137a3dfce17bc9c94648e5ea9e12ec2776195
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377435"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="0288c-103">Het domein kiezen dat u wilt gebruiken voor het maken van Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="0288c-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="0288c-104">Sommige organisaties gebruiken afzonderlijke e-maildomeinen om verschillende onderdelen van het bedrijf te segmenteren.</span><span class="sxs-lookup"><span data-stu-id="0288c-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="0288c-105">U kunt opgeven welk domein moet worden gebruikt wanneer uw gebruikers Microsoft 365-groepen maken.</span><span class="sxs-lookup"><span data-stu-id="0288c-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="0288c-106">Als uw organisatie vereist dat gebruikers hun groepen maken in andere domeinen dan het standaard geaccepteerde domein van uw bedrijf, kunt u dit toestaan door met PowerShell e-mailadresbeleidsregels (EAP's) te configureren.</span><span class="sxs-lookup"><span data-stu-id="0288c-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="0288c-107">Voordat u de PowerShell-cmdlets kunt uitvoeren, downloadt en installeert u een module waarmee u kunt communiceren met uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0288c-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="0288c-108">Zie [Verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881)</span><span class="sxs-lookup"><span data-stu-id="0288c-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="0288c-109">Voorbeelden van scenario's</span><span class="sxs-lookup"><span data-stu-id="0288c-109">Example scenarios</span></span>

<span data-ttu-id="0288c-110">Stel dat Contoso.com het primaire domein van uw bedrijf is.</span><span class="sxs-lookup"><span data-stu-id="0288c-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="0288c-111">Het standaard geaccepteerde domein van uw organisatie is echter service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0288c-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="0288c-112">Dit houdt in dat groepen worden gemaakt in service.contoso.com (bijvoorbeeld jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0288c-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="0288c-113">Stel dat er ook subdomeinen zijn geconfigureerd in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0288c-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="0288c-114">U wilt dat groepen ook in deze domeinen worden gemaakt:</span><span class="sxs-lookup"><span data-stu-id="0288c-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="0288c-115">students.contoso.com voor studenten</span><span class="sxs-lookup"><span data-stu-id="0288c-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="0288c-116">faculty.contoso.com voor faculteitsleden</span><span class="sxs-lookup"><span data-stu-id="0288c-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="0288c-117">In de volgende twee scenario's wordt uitgelegd hoe u dit kunt doen.</span><span class="sxs-lookup"><span data-stu-id="0288c-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="0288c-118">Als u meerdere EAP's hebt, worden deze in volgorde van prioriteit geëvalueerd.</span><span class="sxs-lookup"><span data-stu-id="0288c-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="0288c-119">De waarde 1 betekent de hoogste prioriteit.</span><span class="sxs-lookup"><span data-stu-id="0288c-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="0288c-120">Wanneer u EAP-overeenkomsten maakt, worden er geen verdere EAP geëvalueerd en worden de adressen die een stempel voor de groep bevinden, als volgt vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="0288c-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="0288c-121">Als er > geen Eap's overeenkomen met de opgegeven criteria, wordt de groep ingericht in het standaard geaccepteerd domein van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="0288c-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="0288c-122">Bekijk [Geaccepteerd domeinen beheren in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) voor meer informatie over het toevoegen van een geaccepteerd domein.</span><span class="sxs-lookup"><span data-stu-id="0288c-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="0288c-123">Scenario 1</span><span class="sxs-lookup"><span data-stu-id="0288c-123">Scenario 1</span></span>

<span data-ttu-id="0288c-124">In het volgende voorbeeld ziet u hoe u in het groups.contoso.com-domein alle Microsoft 365-groepen in uw organisatie kunt inrichten.</span><span class="sxs-lookup"><span data-stu-id="0288c-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="0288c-125">Scenario 2</span><span class="sxs-lookup"><span data-stu-id="0288c-125">Scenario 2</span></span>

<span data-ttu-id="0288c-126">Stel dat u wilt bepalen in welke subdomeinen Microsoft 365-groepen worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="0288c-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="0288c-127">U wilt dat:</span><span class="sxs-lookup"><span data-stu-id="0288c-127">You want:</span></span>
  
- <span data-ttu-id="0288c-128">Groepen die zijn gemaakt door studenten (gebruikers voor wie **afdeling** is ingesteld op **studenten**) in het students.groups.contoso.com-domein.</span><span class="sxs-lookup"><span data-stu-id="0288c-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="0288c-129">Gebruik deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="0288c-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="0288c-130">Groepen die zijn gemaakt door leden van de faculteit (gebruikers met een **afdeling** ingesteld op de **docenten of het e-mailadres Faculty.contoso.com)**) in het Faculty.groups.contoso.com-domein.</span><span class="sxs-lookup"><span data-stu-id="0288c-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="0288c-131">Gebruik deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="0288c-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="0288c-132">Groepen die zijn gemaakt door iemand anders, worden gemaakt in het groups.contoso.com-domein.</span><span class="sxs-lookup"><span data-stu-id="0288c-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="0288c-133">Gebruik deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="0288c-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="0288c-134">E-mailadresbeleidsregels wijzigen</span><span class="sxs-lookup"><span data-stu-id="0288c-134">Change email address policies</span></span>

<span data-ttu-id="0288c-135">Gebruik de cmdlet Set-EmailAddressPolicy als u de prioriteit of e-mailadressjablonen voor een bestaand EAP wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0288c-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="0288c-136">Het wijzigen van een EAP heeft geen invloed op de groepen die al zijn ingericht.</span><span class="sxs-lookup"><span data-stu-id="0288c-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="0288c-137">E-mailadresbeleidsregels verwijderen</span><span class="sxs-lookup"><span data-stu-id="0288c-137">Delete email address policies</span></span>

<span data-ttu-id="0288c-138">Gebruik de cmdlet Remove-EmailAddressPolicy om een EAP te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0288c-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="0288c-139">Het wijzigen van een EAP heeft geen invloed op de groepen die al zijn ingericht.</span><span class="sxs-lookup"><span data-stu-id="0288c-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="0288c-140">Hybride vereisten</span><span class="sxs-lookup"><span data-stu-id="0288c-140">Hybrid requirements</span></span>

<span data-ttu-id="0288c-141">Als uw organisatie is geconfigureerd in een hybride scenario, raadpleegt [u Microsoft 365 groepen configureren met on-premises Exchange hybride](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) om ervoor te zorgen dat uw organisatie voldoet aan de vereisten voor het maken van microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="0288c-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="0288c-142">Meer informatie over het gebruik van groepen voor e-mailadres beleidsregels:</span><span class="sxs-lookup"><span data-stu-id="0288c-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="0288c-143">Er zijn nog een paar dingen die u moet weten:</span><span class="sxs-lookup"><span data-stu-id="0288c-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="0288c-144">De snelheid waarmee groepen worden gemaakt, hangt af van het aantal EAP's dat in uw organisatie is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="0288c-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="0288c-145">Beheerders en gebruikers kunnen ook domeinen wijzigen bij het maken van groepen.</span><span class="sxs-lookup"><span data-stu-id="0288c-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="0288c-146">De groep gebruikers wordt bepaald met standaardquery's (Gebruikerseigenschappen), die al beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="0288c-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="0288c-147">Zie [de Befilterbare eigenschappen voor de parameter-RecipientFilter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) voor ondersteunde filter-eigenschappen.</span><span class="sxs-lookup"><span data-stu-id="0288c-147">Check out [Filterable properties for the -RecipientFilter parameter](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="0288c-148">Als u geen EAP's voor groepen configureert, wordt het standaard geaccepteerd domein voor het maken van groepen geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="0288c-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="0288c-149">Als u een geaccepteerd domein verwijdert, moet u eerst de EAP's bijwerken, anders heeft dit invloed op de inrichting van de groep.</span><span class="sxs-lookup"><span data-stu-id="0288c-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="0288c-150">Er kunnen maximaal 100 e-mailadresbeleidsregel voor een organisatie worden geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="0288c-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="0288c-151">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="0288c-151">Related articles</span></span>

[<span data-ttu-id="0288c-152">Een Microsoft 365-groep maken in het Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="0288c-152">Create an Microsoft 365 group in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
