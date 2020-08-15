---
title: Beleidsregels voor Skype voor bedrijven online beheren met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 'Overzicht: PowerShell gebruiken voor het beheren van de eigenschappen van een gebruikersaccount van Skype voor bedrijven online met beleidsregels.'
ms.openlocfilehash: 7657dae6fa1b27299e4cbc0cf6a311380cb90e9e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689404"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="8e50c-103">Beleidsregels voor Skype voor bedrijven online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e50c-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="8e50c-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8e50c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8e50c-105">Als u een groot aantal eigenschappen van een gebruikersaccount voor Skype voor bedrijven online wilt beheren, moet u ze als eigenschappen van het beleid opgeven met PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e50c-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="8e50c-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="8e50c-106">Before you begin</span></span>

<span data-ttu-id="8e50c-107">Voer de volgende instructies uit om de opdrachten uit te voeren (u kunt de stappen die u al hebt voltooid overslaan):</span><span class="sxs-lookup"><span data-stu-id="8e50c-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
1. <span data-ttu-id="8e50c-108">Download en installeer de [connector module van Skype voor bedrijven online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="8e50c-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
    
2. <span data-ttu-id="8e50c-109">Open een Windows PowerShell-opdrachtprompt en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="8e50c-109">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
  ```

<span data-ttu-id="8e50c-110">Voer uw beheerdersaccount naam en wachtwoord voor Skype voor bedrijven online in wanneer hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="8e50c-110">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="8e50c-111">Beleidsregels voor gebruikersaccounts beheren</span><span class="sxs-lookup"><span data-stu-id="8e50c-111">Manage user account policies</span></span>

<span data-ttu-id="8e50c-112">Veel eigenschappen van een gebruikersaccount van Skype voor bedrijven online worden geconfigureerd met behulp van beleid.</span><span class="sxs-lookup"><span data-stu-id="8e50c-112">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="8e50c-113">Beleidsregels zijn simpelweg verzamelingen met instellingen die kunnen worden toegepast op een of meer gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8e50c-113">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="8e50c-114">Als u wilt bekijken hoe het beleid is geconfigureerd, kunt u dit voorbeeld-opdracht uitvoeren voor het FederationAndPICDefault-beleid:</span><span class="sxs-lookup"><span data-stu-id="8e50c-114">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="8e50c-115">Op de beurt moet u iets op de volgende manier weergeven:</span><span class="sxs-lookup"><span data-stu-id="8e50c-115">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="8e50c-116">In dit voorbeeld bepalen de waarden binnen dit beleid wat een gebruik of niet kan doen wanneer het gaat om communiceren met federatieve gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8e50c-116">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="8e50c-117">Als u bijvoorbeeld wilt dat een gebruiker kan communiceren met personen buiten de organisatie, moet de eigenschap EnableOutsideAccess zijn ingesteld op waar.</span><span class="sxs-lookup"><span data-stu-id="8e50c-117">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="8e50c-118">Deze eigenschap wordt niet weergegeven in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="8e50c-118">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8e50c-119">In plaats daarvan wordt de eigenschap automatisch ingesteld op waar of onwaar, op basis van de andere selecties die u aanbrengt.</span><span class="sxs-lookup"><span data-stu-id="8e50c-119">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="8e50c-120">De andere twee eigenschappen van belang zijn:</span><span class="sxs-lookup"><span data-stu-id="8e50c-120">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="8e50c-121">**EnableFederationAccess** geeft aan of de gebruiker kan communiceren met mensen van federatieve domeinen.</span><span class="sxs-lookup"><span data-stu-id="8e50c-121">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="8e50c-122">**EnablePublicCloudAccess** geeft aan of de gebruiker kan communiceren met Windows Live-gebruikers.</span><span class="sxs-lookup"><span data-stu-id="8e50c-122">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="8e50c-123">U kunt dus niet rechtstreeks Federatie gerelateerde eigenschappen wijzigen voor gebruikersaccounts (bijvoorbeeld **set-CsUser-EnableFederationAccess $True**).</span><span class="sxs-lookup"><span data-stu-id="8e50c-123">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="8e50c-124">U kunt in plaats daarvan een extern toegangsbeleid toewijzen waarbij de gewenste eigenschapswaarden vooraf zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="8e50c-124">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="8e50c-125">Als u wilt dat een gebruiker kan communiceren met federatieve gebruikers en met Windows Live-gebruikers, moet aan die gebruikersaccount een beleid worden toegewezen dat de communicatie tussen deze typen toestaat.</span><span class="sxs-lookup"><span data-stu-id="8e50c-125">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="8e50c-126">Als u wilt weten of iemand met gebruikers van buiten de organisatie kan communiceren, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="8e50c-126">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="8e50c-127">Bepaal welk extern toegangsbeleid is toegewezen aan deze gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8e50c-127">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="8e50c-128">Bepalen welke mogelijkheden wel of niet zijn toegestaan door het beleid.</span><span class="sxs-lookup"><span data-stu-id="8e50c-128">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="8e50c-129">U kunt bijvoorbeeld de volgende opdracht gebruiken:</span><span class="sxs-lookup"><span data-stu-id="8e50c-129">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="8e50c-130">Met deze opdracht vindt u het beleid dat is toegewezen aan de gebruiker en vindt u vervolgens de functies die zijn ingeschakeld of uitgeschakeld binnen dat beleid.</span><span class="sxs-lookup"><span data-stu-id="8e50c-130">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="8e50c-131">Als u het beleid van Skype voor bedrijven online wilt beheren met PowerShell, raadpleegt u de cmdlets voor:</span><span class="sxs-lookup"><span data-stu-id="8e50c-131">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="8e50c-132">[Client beleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="8e50c-132">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="8e50c-133">[Vergader beleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="8e50c-133">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="8e50c-134">[Mobiel beleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="8e50c-134">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="8e50c-135">[Online voicemail beleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="8e50c-135">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="8e50c-136">[Routeringsbeleid voor spraak](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="8e50c-136">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="8e50c-137">Een Skype voor bedrijven online-Kies plan is voor elk opzicht een beleid met uitzondering van de naam.</span><span class="sxs-lookup"><span data-stu-id="8e50c-137">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="8e50c-138">Voor de compatibiliteit met Office Communications Server en Exchange is de naam ' Kies plan ' in plaats van ' Kies beleid ' gekozen.</span><span class="sxs-lookup"><span data-stu-id="8e50c-138">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="8e50c-139">Voer de volgende opdracht uit om alle voicemail beleidsregels te bekijken die voor uw gebruik beschikbaar zijn:</span><span class="sxs-lookup"><span data-stu-id="8e50c-139">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="8e50c-140">Hiermee wordt een lijst geretourneerd met alle voicemail beleidsregels die beschikbaar zijn voor u.</span><span class="sxs-lookup"><span data-stu-id="8e50c-140">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="8e50c-141">Houd er rekening mee dat u niet alle beleidsregels aan alle gebruikers kunt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="8e50c-141">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="8e50c-142">Dit wordt veroorzaakt door verschillende beperkingen met betrekking tot licentieverlening en geografische ligging.</span><span class="sxs-lookup"><span data-stu-id="8e50c-142">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="8e50c-143">(De zogenaamde[gebruikslocatie](https://msdn.microsoft.com/library/azure/dn194136.aspx)) Als u wilt weten hoe het beleid voor externe toegang en het beleid voor vergaderen dat aan een bepaalde gebruiker kan worden toegewezen, kunt u vinden in de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="8e50c-143">(The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="8e50c-144">Met de ApplicableTo-parameter wordt de geretourneerde gegevens gelimiteerd aan beleidsregels die kunnen worden toegewezen aan de opgegeven gebruiker (bijvoorbeeld Alex Darrow).</span><span class="sxs-lookup"><span data-stu-id="8e50c-144">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow).</span></span> <span data-ttu-id="8e50c-145">Afhankelijk van de beperkingen voor locatie van licentie en gebruik van een locatie, kunt u een subset van alle beschikbare beleidsregels vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="8e50c-145">Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="8e50c-146">In sommige gevallen worden de eigenschappen van beleidsregels niet gebruikt met Microsoft 365, terwijl andere personen de medewerkers van Microsoft ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="8e50c-146">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="8e50c-147">Met Skype voor bedrijven online dienen gebruikers een beleid van enige aard te beheren.</span><span class="sxs-lookup"><span data-stu-id="8e50c-147">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="8e50c-148">Als een geldige eigenschap voor het beleid leeg is, betekent dit dat de aangevraagde gebruiker wordt beheerd door een algemeen beleid, dat een beleid is dat automatisch wordt toegepast op een gebruiker, tenzij hij of zij specifiek een beleid per gebruiker toewijst.</span><span class="sxs-lookup"><span data-stu-id="8e50c-148">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="8e50c-149">Aangezien er geen clientbeleid wordt weergegeven voor een gebruikersaccount, wordt dit beheerd door het globale beleid.</span><span class="sxs-lookup"><span data-stu-id="8e50c-149">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="8e50c-150">U kunt het beleid voor globale clients bepalen met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="8e50c-150">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="8e50c-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8e50c-151">See also</span></span>

[<span data-ttu-id="8e50c-152">Skype voor bedrijven online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e50c-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8e50c-153">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e50c-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8e50c-154">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8e50c-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

