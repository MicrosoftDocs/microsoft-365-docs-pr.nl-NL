---
title: Een onlinebeleid Skype voor Bedrijven per gebruiker toewijzen met PowerShell voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 'Overzicht: Gebruik PowerShell voor Microsoft 365 om communicatie-instellingen per gebruiker toe te wijzen met Skype voor Bedrijven Online-beleid.'
ms.openlocfilehash: 2d3d953fe0beb74cc63f914137942f068ce90be7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905402"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="158c9-103">Een onlinebeleid Skype voor Bedrijven per gebruiker toewijzen met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="158c9-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="158c9-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="158c9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="158c9-105">PowerShell gebruiken voor Microsoft 365 is een efficiënte manier om communicatie-instellingen per gebruiker toe te wijzen met Skype voor Bedrijven Online-beleid.</span><span class="sxs-lookup"><span data-stu-id="158c9-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="158c9-106">De PowerShell-opdrachten voorbereiden</span><span class="sxs-lookup"><span data-stu-id="158c9-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="158c9-107">Gebruik deze instructies om de opdrachten uit te voeren (sla de stappen over die u al hebt voltooid):</span><span class="sxs-lookup"><span data-stu-id="158c9-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="158c9-108">Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="158c9-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="158c9-109">Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.</span><span class="sxs-lookup"><span data-stu-id="158c9-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="158c9-110">Installeer de [Teams PowerShell-module](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="158c9-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="158c9-111">Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="158c9-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="158c9-112">Wanneer u hier om wordt gevraagd, voert u Skype voor Bedrijven naam en wachtwoord van uw onlinebeheerdersaccount in.</span><span class="sxs-lookup"><span data-stu-id="158c9-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="158c9-113">Externe communicatie-instellingen voor een gebruikersaccount bijwerken</span><span class="sxs-lookup"><span data-stu-id="158c9-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="158c9-114">Stel dat u instellingen voor externe communicatie in een gebruikersaccount wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="158c9-114">Suppose you want to change external communication settings on a user account.</span></span> <span data-ttu-id="158c9-115">U wilt bijvoorbeeld toestaan dat Alex communiceert met federatieve gebruikers (EnableFederationAccess is gelijk aan Waar), maar niet met Windows Live-gebruikers (EnablePublicCloudAccess is gelijk aan Onwaar).</span><span class="sxs-lookup"><span data-stu-id="158c9-115">For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False).</span></span> <span data-ttu-id="158c9-116">Om dat te doen, moet u twee dingen doen:</span><span class="sxs-lookup"><span data-stu-id="158c9-116">To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="158c9-117">Zoek een beleid voor externe toegang dat voldoet aan onze criteria.</span><span class="sxs-lookup"><span data-stu-id="158c9-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="158c9-118">Wijs dat beleid voor externe toegang toe aan Alex.</span><span class="sxs-lookup"><span data-stu-id="158c9-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="158c9-119">Hoe bepaalt u welk beleid voor externe toegang u Alex wilt toewijzen?</span><span class="sxs-lookup"><span data-stu-id="158c9-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="158c9-120">De volgende opdracht retourneert alle beleidsregels voor externe toegang waarin EnableFederationAccess is ingesteld op Waar en EnablePublicCloudAccess is ingesteld op Onwaar:</span><span class="sxs-lookup"><span data-stu-id="158c9-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="158c9-121">Tenzij u aangepaste exemplaren van ExternalAccessPolicy hebt gemaakt, retourneert deze opdracht één beleid dat voldoet aan onze criteria (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="158c9-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="158c9-122">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="158c9-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="158c9-123">Nu u weet welk beleid aan Alex moet worden toegewezen, kunnen we dat beleid toewijzen met behulp van de [cmdlet Grant-CsExternalAccessPolicy.](/powershell/module/skype/Get-CsExternalAccessPolicy)</span><span class="sxs-lookup"><span data-stu-id="158c9-123">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet.</span></span> <span data-ttu-id="158c9-124">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="158c9-124">Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="158c9-125">Het toewijzen van een beleid is vrij eenvoudig: u geeft alleen de identiteit van de gebruiker op en de naam van het beleid dat moet worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="158c9-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="158c9-126">En als het gaat om beleid en beleidstoewijzingen, kunt u niet alleen één keer met gebruikersaccounts werken.</span><span class="sxs-lookup"><span data-stu-id="158c9-126">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time.</span></span> <span data-ttu-id="158c9-127">Stel dat u een lijst nodig hebt met alle gebruikers die mogen communiceren met federatieve partners en met Windows Live-gebruikers.</span><span class="sxs-lookup"><span data-stu-id="158c9-127">For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users.</span></span> <span data-ttu-id="158c9-128">We weten al dat aan deze gebruikers het beleid voor externe gebruikerstoegang FederationAndPICDefault is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="158c9-128">We already know that those users have been assigned the external user access policy FederationAndPICDefault.</span></span> <span data-ttu-id="158c9-129">Omdat we dat weten, kunt u een lijst met al die gebruikers weergeven door één eenvoudige opdracht uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="158c9-129">Because we know that, you can display a list of all those users by running one simple command.</span></span> <span data-ttu-id="158c9-130">Hier is de opdracht:</span><span class="sxs-lookup"><span data-stu-id="158c9-130">Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="158c9-131">Met andere woorden, laat ons alle gebruikers zien waar de eigenschap ExternalAccessPolicy is ingesteld op FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="158c9-131">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault.</span></span> <span data-ttu-id="158c9-132">(En als u de hoeveelheid informatie op het scherm wilt beperken, gebruikt u de cmdlet Select-Object om alleen de weergavenaam van elke gebruiker weer te geven.)</span><span class="sxs-lookup"><span data-stu-id="158c9-132">(And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="158c9-133">Als u al onze gebruikersaccounts wilt configureren om hetzelfde beleid te gebruiken, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="158c9-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="158c9-134">Deze opdracht gebruikt Get-CsOnlineUser om een verzameling van alle gebruikers te retourneren die zijn ingeschakeld voor Lync en stuurt vervolgens al deze informatie naar Grant-CsExternalAccessPolicy, waarmee het FederationAndPICDefault-beleid aan elke gebruiker in de verzameling wordt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="158c9-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="158c9-135">Stel dat u Alex eerder het FederationAndPICDefault-beleid hebt toegewezen en nu bent u van gedachten veranderd en wilt u dat hij wordt beheerd door het globale beleid voor externe toegang.</span><span class="sxs-lookup"><span data-stu-id="158c9-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="158c9-136">U kunt het globale beleid niet expliciet aan iemand toewijzen.</span><span class="sxs-lookup"><span data-stu-id="158c9-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="158c9-137">In plaats daarvan wordt het algemene beleid voor een bepaalde gebruiker gebruikt als er geen beleid per gebruiker aan die gebruiker is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="158c9-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="158c9-138">Daarom, als we willen dat Alex wordt beheerd  door het globale beleid, moet u een beleid per gebruiker dat eerder aan hem is toegewezen, niet toewijzen.</span><span class="sxs-lookup"><span data-stu-id="158c9-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="158c9-139">Hier is een voorbeeldopdracht:</span><span class="sxs-lookup"><span data-stu-id="158c9-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="158c9-140">Met deze opdracht wordt de naam van het beleid voor externe toegang dat aan Alex is toegewezen, ingedeeld in een null-waarde ($Null).</span><span class="sxs-lookup"><span data-stu-id="158c9-140">This command sets the name of the external access policy assigned to Alex to a null value ($Null).</span></span> <span data-ttu-id="158c9-141">Null betekent 'niets'.</span><span class="sxs-lookup"><span data-stu-id="158c9-141">Null means "nothing".</span></span> <span data-ttu-id="158c9-142">Met andere woorden, er is geen beleid voor externe toegang toegewezen aan Alex.</span><span class="sxs-lookup"><span data-stu-id="158c9-142">In other words, no external access policy is assigned to Alex.</span></span> <span data-ttu-id="158c9-143">Als er geen beleid voor externe toegang is toegewezen aan een gebruiker, wordt deze gebruiker vervolgens beheerd door het globale beleid.</span><span class="sxs-lookup"><span data-stu-id="158c9-143">When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>
  

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="158c9-144">Grote aantallen gebruikers beheren</span><span class="sxs-lookup"><span data-stu-id="158c9-144">Managing large numbers of users</span></span>

<span data-ttu-id="158c9-145">Als u grote aantallen gebruikers (1000 of meer) wilt beheren, moet u de opdrachten batcheren via een scriptblok met de cmdlet [Invoke-Command.](/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="158c9-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet.</span></span>  <span data-ttu-id="158c9-146">In eerdere voorbeelden moet elke keer dat een cmdlet wordt uitgevoerd, de oproep worden ingesteld en vervolgens wachten op het resultaat voordat u deze terug verstuurt.</span><span class="sxs-lookup"><span data-stu-id="158c9-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="158c9-147">Wanneer u een scriptblok gebruikt, kunnen de cmdlets op afstand worden uitgevoerd en de gegevens terugsturen wanneer ze zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="158c9-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span> 

```powershell
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

<span data-ttu-id="158c9-148">Hier vindt u 500 gebruikers tegelijk die geen clientbeleid hebben.</span><span class="sxs-lookup"><span data-stu-id="158c9-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="158c9-149">De klant krijgt het clientbeleid 'ClientPolicyNoIMURL' en het beleid voor externe toegang 'FederationAndPicDefault'.</span><span class="sxs-lookup"><span data-stu-id="158c9-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="158c9-150">De resultaten worden in groepen van 50 batched en elke batch van 50 wordt vervolgens naar de externe computer verzonden.</span><span class="sxs-lookup"><span data-stu-id="158c9-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="158c9-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="158c9-151">See also</span></span>

[<span data-ttu-id="158c9-152">Skype voor Bedrijven Online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="158c9-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="158c9-153">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="158c9-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="158c9-154">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="158c9-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)