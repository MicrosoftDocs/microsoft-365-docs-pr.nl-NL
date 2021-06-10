---
title: Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell
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
description: 'Overzicht: Gebruik PowerShell om de eigenschappen Skype voor Bedrijven onlinegebruikersaccount met beleid te beheren.'
ms.openlocfilehash: a10929bbdce499ad26f9714127f675beeef58765
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916700"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="0b81d-103">Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b81d-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="0b81d-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0b81d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0b81d-105">Als u veel eigenschappen van gebruikersaccounts voor Skype voor Bedrijven Online wilt beheren, moet u deze opgeven als eigenschappen van beleidsregels met PowerShell voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0b81d-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="0b81d-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="0b81d-106">Before you begin</span></span>

<span data-ttu-id="0b81d-107">Gebruik deze instructies om de opdrachten uit te voeren (sla de stappen over die u al hebt voltooid):</span><span class="sxs-lookup"><span data-stu-id="0b81d-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>

  > [!Note]
  > <span data-ttu-id="0b81d-108">Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="0b81d-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="0b81d-109">Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.</span><span class="sxs-lookup"><span data-stu-id="0b81d-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="0b81d-110">Installeer de [Teams PowerShell-module](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="0b81d-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="0b81d-111">Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="0b81d-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   <span data-ttu-id="0b81d-112">Wanneer u hier om wordt gevraagd, voert u Skype voor Bedrijven naam en wachtwoord van uw onlinebeheerdersaccount in.</span><span class="sxs-lookup"><span data-stu-id="0b81d-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="0b81d-113">Beleidsregels voor gebruikersaccounts beheren</span><span class="sxs-lookup"><span data-stu-id="0b81d-113">Manage user account policies</span></span>

<span data-ttu-id="0b81d-114">Veel Skype voor Bedrijven eigenschappen van onlinegebruikersaccounts worden geconfigureerd met behulp van beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="0b81d-114">Many Skype for Business Online user account properties are configured by using policies.</span></span> <span data-ttu-id="0b81d-115">Beleidsregels zijn gewoon verzamelingen met instellingen die kunnen worden toegepast op een of meer gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0b81d-115">Policies are simply collections of settings that can be applied to one or more users.</span></span> <span data-ttu-id="0b81d-116">Als u wilt bekijken hoe het beleid is geconfigureerd, kunt u deze voorbeeldopdracht uitvoeren voor het FederationAndPICDefault-beleid:</span><span class="sxs-lookup"><span data-stu-id="0b81d-116">To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="0b81d-117">Op zijn beurt moet u iets dergelijks als dit terug krijgen:</span><span class="sxs-lookup"><span data-stu-id="0b81d-117">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="0b81d-118">In dit voorbeeld bepalen de waarden in dit beleid wat een gebruik wel of niet kan doen als het gaat om communiceren met federatief gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0b81d-118">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="0b81d-119">De eigenschap EnableOutsideAccess moet bijvoorbeeld zijn ingesteld op Waar zodat een gebruiker kan communiceren met personen buiten de organisatie.</span><span class="sxs-lookup"><span data-stu-id="0b81d-119">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="0b81d-120">Houd er rekening mee dat deze eigenschap niet wordt weergegeven in het Microsoft 365 beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="0b81d-120">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0b81d-121">In plaats daarvan wordt de eigenschap automatisch ingesteld op Waar of Onwaar op basis van de andere selecties die u maakt.</span><span class="sxs-lookup"><span data-stu-id="0b81d-121">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="0b81d-122">De andere twee eigenschappen van belang zijn:</span><span class="sxs-lookup"><span data-stu-id="0b81d-122">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="0b81d-123">**EnableFederationAccess** geeft aan of de gebruiker kan communiceren met personen uit federatief domeinen.</span><span class="sxs-lookup"><span data-stu-id="0b81d-123">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="0b81d-124">**EnablePublicCloudAccess** geeft aan of de gebruiker kan communiceren met Windows Live-gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0b81d-124">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="0b81d-125">Daarom wijzigt u niet rechtstreeks federatie-gerelateerde eigenschappen op gebruikersaccounts (bijvoorbeeld **Set-CsUser -EnableFederationAccess $True).**</span><span class="sxs-lookup"><span data-stu-id="0b81d-125">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**).</span></span> <span data-ttu-id="0b81d-126">In plaats daarvan wijst u een account een beleid voor externe toegang toe dat de gewenste eigenschapswaarden vooraf heeft geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="0b81d-126">Instead, you assign an account an external access policy that has the desired property values preconfigured.</span></span> <span data-ttu-id="0b81d-127">Als we willen dat een gebruiker kan communiceren met federatieve gebruikers en met Windows Live-gebruikers, moet aan dat gebruikersaccount een beleid worden toegewezen waarmee deze typen communicatie mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="0b81d-127">If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="0b81d-128">Als u wilt weten of iemand kan communiceren met gebruikers van buiten de organisatie, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="0b81d-128">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="0b81d-129">Bepaal welk beleid voor externe toegang aan die gebruiker is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0b81d-129">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="0b81d-130">Bepaal welke mogelijkheden wel of niet zijn toegestaan in dat beleid.</span><span class="sxs-lookup"><span data-stu-id="0b81d-130">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="0b81d-131">U kunt dit bijvoorbeeld doen met deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="0b81d-131">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="0b81d-132">Met deze opdracht wordt het beleid gevonden dat aan de gebruiker is toegewezen en worden vervolgens de mogelijkheden gevonden die in dat beleid zijn ingeschakeld of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0b81d-132">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="0b81d-133">Zie de cmdlets voor Skype voor Bedrijven onlinebeleid beheren met PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0b81d-133">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="0b81d-134">[Clientbeleid](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="0b81d-134">[Client policy](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="0b81d-135">[Conferencingbeleid](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="0b81d-135">[Conferencing policy](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="0b81d-136">[Mobiel beleid](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="0b81d-136">[Mobile policy](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="0b81d-137">[Beleid voor online voicemail](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="0b81d-137">[Online Voicemail policy](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="0b81d-138">[Beleid voor spraakroutering](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="0b81d-138">[Voice Routing policy](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="0b81d-139">Een Skype voor Bedrijven Online-kiesplan is in alle opzichten een beleid, behalve de naam.</span><span class="sxs-lookup"><span data-stu-id="0b81d-139">A Skype for Business Online dial plan is a policy in every respect except the name.</span></span> <span data-ttu-id="0b81d-140">De naam 'kiesplan' is gekozen in plaats van bijvoorbeeld 'kiesbeleid' om achterwaartse compatibiliteit te bieden met Office Communications Server en met Exchange.</span><span class="sxs-lookup"><span data-stu-id="0b81d-140">The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="0b81d-141">Als u bijvoorbeeld alle spraakbeleidsregels wilt bekijken die beschikbaar zijn voor uw gebruik, voer dan deze opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="0b81d-141">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="0b81d-142">Dit geeft als return een lijst met alle spraakbeleidsregels die beschikbaar zijn voor u.</span><span class="sxs-lookup"><span data-stu-id="0b81d-142">That returns a list of all the voice policies available to you.</span></span> <span data-ttu-id="0b81d-143">Houd er echter rekening mee dat niet alle beleidsregels aan alle gebruikers kunnen worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0b81d-143">Keep in mind, however, that not all policies can be assigned to all users.</span></span> <span data-ttu-id="0b81d-144">Dit komt door verschillende beperkingen met betrekking tot licenties en geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="0b81d-144">This is due to various restrictions involving licensing and geographic location.</span></span> <span data-ttu-id="0b81d-145">(De zogenaamde "[gebruikslocatie](/previous-versions/azure/dn194136(v=azure.100)).") Als u wilt weten wat het beleid voor externe toegang is en welke beleidsregels voor conferencing aan een bepaalde gebruiker kunnen worden toegewezen, gebruikt u opdrachten die vergelijkbaar zijn met deze:</span><span class="sxs-lookup"><span data-stu-id="0b81d-145">(The so-called "[usage location](/previous-versions/azure/dn194136(v=azure.100)).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="0b81d-146">De parameter ApplicableTo beperkt de geretourneerde gegevens tot beleid dat kan worden toegewezen aan de opgegeven gebruiker (bijvoorbeeld Alex Darrow).</span><span class="sxs-lookup"><span data-stu-id="0b81d-146">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow).</span></span> <span data-ttu-id="0b81d-147">Afhankelijk van licentie- en gebruikslocatiebeperkingen kan dit een subset van alle beschikbare beleidsregels vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="0b81d-147">Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="0b81d-148">In sommige gevallen worden eigenschappen van beleid niet gebruikt met Microsoft 365, terwijl andere alleen kunnen worden beheerd door ondersteuningsmedewerkers van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0b81d-148">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="0b81d-149">Met Skype voor Bedrijven Online moeten gebruikers worden beheerd door een beleid van een bepaalde soort.</span><span class="sxs-lookup"><span data-stu-id="0b81d-149">With Skype for Business Online, users must be managed by a policy of some kind.</span></span> <span data-ttu-id="0b81d-150">Als een geldige beleidsgerelateerde eigenschap leeg is, betekent dit dat de gebruiker in kwestie wordt beheerd door een globaal beleid. Dit is een beleid dat automatisch wordt toegepast op een gebruiker, tenzij aan hem of haar specifiek een beleid per gebruiker is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0b81d-150">If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy.</span></span> <span data-ttu-id="0b81d-151">Omdat er geen clientbeleid wordt weergegeven voor een gebruikersaccount, wordt het beheerd door het algemene beleid.</span><span class="sxs-lookup"><span data-stu-id="0b81d-151">Because we don't see a client policy listed for a user account, it is managed by the global policy.</span></span> <span data-ttu-id="0b81d-152">Met deze opdracht kunt u het globale clientbeleid bepalen:</span><span class="sxs-lookup"><span data-stu-id="0b81d-152">You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="0b81d-153">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0b81d-153">See also</span></span>

[<span data-ttu-id="0b81d-154">Skype voor Bedrijven Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b81d-154">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0b81d-155">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b81d-155">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0b81d-156">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b81d-156">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)