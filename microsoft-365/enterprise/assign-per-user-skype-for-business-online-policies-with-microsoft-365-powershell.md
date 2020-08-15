---
title: Beleidsregels voor Skype voor bedrijven online toewijzen aan een gebruiker met PowerShell voor Microsoft 365
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
description: 'Samenvatting: gebruik PowerShell voor Microsoft 365 om communicatie-instellingen per gebruiker toe te wijzen aan het beleid van Skype voor bedrijven online.'
ms.openlocfilehash: 6ff9fce3e0287313f6725b370b6ba89cb939eb3a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689193"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="0b146-103">Beleidsregels voor Skype voor bedrijven online toewijzen aan een gebruiker met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b146-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="0b146-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0b146-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0b146-105">Het gebruik van PowerShell voor Microsoft 365 is een efficiënte manier om communicatie-instellingen per gebruiker toe te wijzen aan het beleid van Skype voor bedrijven online.</span><span class="sxs-lookup"><span data-stu-id="0b146-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="0b146-106">Het uitvoeren van de PowerShell-opdrachten voorbereiden</span><span class="sxs-lookup"><span data-stu-id="0b146-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="0b146-107">Voer de volgende instructies uit om de opdrachten uit te voeren (u kunt de stappen die u al hebt voltooid overslaan):</span><span class="sxs-lookup"><span data-stu-id="0b146-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
1. <span data-ttu-id="0b146-108">Download en installeer de [connector module van Skype voor bedrijven online](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="0b146-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
    
2. <span data-ttu-id="0b146-109">Open een Windows PowerShell-opdrachtprompt en voer de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="0b146-109">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
```powershell
Import-Module LyncOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

<span data-ttu-id="0b146-110">Voer uw beheerdersaccount naam en wachtwoord voor Skype voor bedrijven online in wanneer hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="0b146-110">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="0b146-111">Instellingen voor externe communicatie voor een gebruikersaccount bijwerken</span><span class="sxs-lookup"><span data-stu-id="0b146-111">Updating external communication settings for a user account</span></span>

<span data-ttu-id="0b146-112">Stel dat u de instellingen voor externe communicatie voor een gebruikersaccount wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0b146-112">Suppose you want to change external communication settings on a user account.</span></span> <span data-ttu-id="0b146-113">U wilt bijvoorbeeld het voor de communicatie met federatieve gebruikers toestaan (EnableFederationAccess is gelijk aan waar), maar niet met Windows Live-gebruikers (EnablePublicCloudAccess is gelijk aan onwaar).</span><span class="sxs-lookup"><span data-stu-id="0b146-113">For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False).</span></span> <span data-ttu-id="0b146-114">Hiervoor moet u twee dingen doen:</span><span class="sxs-lookup"><span data-stu-id="0b146-114">To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="0b146-115">Zoek een extern toegangsbeleid dat aan de criteria voldoet.</span><span class="sxs-lookup"><span data-stu-id="0b146-115">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="0b146-116">Wijs dit externe toegangsbeleid toe aan Alex.</span><span class="sxs-lookup"><span data-stu-id="0b146-116">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="0b146-117">Hoe bepaal ik welk externe toegangsbeleid moet worden toegewezen aan een Alex?</span><span class="sxs-lookup"><span data-stu-id="0b146-117">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="0b146-118">Met de volgende opdracht worden alle externe toegangs beleidsregels geretourneerd waarbij EnableFederationAccess is ingesteld op waar en EnablePublicCloudAccess is ingesteld op ONWAAR:</span><span class="sxs-lookup"><span data-stu-id="0b146-118">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="0b146-119">Als u een aangepaste instantie van ExternalAccessPolicy hebt gemaakt, wordt door die opdracht één beleid geretourneerd dat voldoet aan de criteria (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="0b146-119">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="0b146-120">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0b146-120">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="0b146-121">Nu u weet welk beleid moet worden toegewezen aan het Alex, kunnen we dit beleid toewijzen met behulp van de cmdlet [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) .</span><span class="sxs-lookup"><span data-stu-id="0b146-121">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) cmdlet.</span></span> <span data-ttu-id="0b146-122">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0b146-122">Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="0b146-123">Het toewijzen van een beleid is tamelijk simpel: u geeft simpelweg de identiteit van de gebruiker op en de naam van het beleid dat u wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="0b146-123">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="0b146-124">En wanneer het gaat om beleidsregels en beleidstoewijzingen, kunt u niet beperkt werken met gebruikersaccounts één keer.</span><span class="sxs-lookup"><span data-stu-id="0b146-124">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time.</span></span> <span data-ttu-id="0b146-125">Stel dat u een lijst met alle gebruikers wilt hebben die kunnen communiceren met federatieve partners en met Windows Live-gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0b146-125">For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users.</span></span> <span data-ttu-id="0b146-126">U weet al dat aan deze gebruikers het externe beleid voor gebruikers toegang FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="0b146-126">We already know that those users have been assigned the external user access policy FederationAndPICDefault.</span></span> <span data-ttu-id="0b146-127">Aangezien we weten dat u een lijst met al deze gebruikers kunt weergeven, voert u één eenvoudige opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="0b146-127">Because we know that, you can display a list of all those users by running one simple command.</span></span> <span data-ttu-id="0b146-128">Dit is de opdracht:</span><span class="sxs-lookup"><span data-stu-id="0b146-128">Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="0b146-129">Met andere woorden: Toon ons alle gebruikers waar de eigenschap ExternalAccessPolicy is ingesteld op FederationAndPICDefault.</span><span class="sxs-lookup"><span data-stu-id="0b146-129">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault.</span></span> <span data-ttu-id="0b146-130">(En als u de hoeveelheid gegevens die op het scherm wordt weergegeven wilt beperken, gebruikt u de cmdlet select-object om de weergave van de gebruikersnaam weer te geven.)</span><span class="sxs-lookup"><span data-stu-id="0b146-130">(And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="0b146-131">Als u al uw gebruikersaccounts wilt configureren voor gebruik van dit beleid, gebruikt u deze opdracht:</span><span class="sxs-lookup"><span data-stu-id="0b146-131">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="0b146-132">Deze opdracht maakt gebruik van Get-CsOnlineUser om een verzameling te retourneren van alle gebruikers die zijn ingeschakeld voor Lync, en stuurt vervolgens al die informatie naar Grant-CsExternalAccessPolicy, waarmee het FederationAndPICDefault-beleid wordt toegewezen aan elke gebruiker in de verzameling.</span><span class="sxs-lookup"><span data-stu-id="0b146-132">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="0b146-133">Voorbeeld van een ander voorbeeld hebt u het FederationAndPICDefault-beleid eerder toegewezen en bent u van gedachten veranderd, en zou u ze wilt laten beheren door het globale externe toegangsbeleid.</span><span class="sxs-lookup"><span data-stu-id="0b146-133">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="0b146-134">U kunt het globale beleid niet expliciet aan iedereen toewijzen.</span><span class="sxs-lookup"><span data-stu-id="0b146-134">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="0b146-135">In plaats daarvan wordt het globale beleid gebruikt voor een bepaalde gebruiker als het beleid voor de gebruiker niet is toegewezen aan deze gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0b146-135">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="0b146-136">En als we willen dat de instelling wordt beheerd door het globale beleid, moet u dit beleid voor gebruikers die eerder aan de gebruiker zijn toegewezen,  *intrekken*  .</span><span class="sxs-lookup"><span data-stu-id="0b146-136">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="0b146-137">Hier ziet u een voorbeeld van een opdracht:</span><span class="sxs-lookup"><span data-stu-id="0b146-137">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="0b146-138">Met deze opdracht stelt u de naam in van het externe toegangsbeleid dat is toegewezen aan Alex met een null-waarde ($Null).</span><span class="sxs-lookup"><span data-stu-id="0b146-138">This command sets the name of the external access policy assigned to Alex to a null value ($Null).</span></span> <span data-ttu-id="0b146-139">Null betekent ' niets '.</span><span class="sxs-lookup"><span data-stu-id="0b146-139">Null means "nothing".</span></span> <span data-ttu-id="0b146-140">Er worden dus geen beleid voor externe toegang toegewezen aan Alex.</span><span class="sxs-lookup"><span data-stu-id="0b146-140">In other words, no external access policy is assigned to Alex.</span></span> <span data-ttu-id="0b146-141">Wanneer er geen extern toegangsbeleid aan een gebruiker is toegewezen, wordt die gebruiker dan beheerd door het globale beleid.</span><span class="sxs-lookup"><span data-stu-id="0b146-141">When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>
  

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="0b146-142">Grote aantallen gebruikers beheren</span><span class="sxs-lookup"><span data-stu-id="0b146-142">Managing large numbers of users</span></span>

<span data-ttu-id="0b146-143">Als u een groot aantal gebruikers wilt beheren (1000 of meer), moet u de opdrachten batchgewijs batchiseren via een scriptblok met de cmdlet [invoke-opdracht](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) .</span><span class="sxs-lookup"><span data-stu-id="0b146-143">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) cmdlet.</span></span>  <span data-ttu-id="0b146-144">In vorige voorbeelden moet de verbinding telkens wanneer een cmdlet wordt uitgevoerd, worden ingesteld en wordt het resultaat weergegeven voordat u het bericht verzendt.</span><span class="sxs-lookup"><span data-stu-id="0b146-144">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="0b146-145">Wanneer u een scriptblok gebruikt, kunt u hiermee de cmdlets extern uitvoeren en de gegevens terug verzenden.</span><span class="sxs-lookup"><span data-stu-id="0b146-145">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span> 

```powershell
Import-Module LyncOnlineConnector
$sfbSession = New-CsOnlineSession
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

<span data-ttu-id="0b146-146">Met deze optie worden 500-gebruikers tegelijk gezocht die geen clientbeleid hebben.</span><span class="sxs-lookup"><span data-stu-id="0b146-146">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="0b146-147">Het beleid voor de client ' ClientPolicyNoIMURL ' en het externe toegangsbeleid ' FederationAndPicDefault ' wordt toegekend.</span><span class="sxs-lookup"><span data-stu-id="0b146-147">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="0b146-148">De resultaten worden batchgewijs omgezet in groepen van 50 en elke batch van 50 wordt vervolgens naar de externe computer verzonden.</span><span class="sxs-lookup"><span data-stu-id="0b146-148">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b146-149">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0b146-149">See also</span></span>

[<span data-ttu-id="0b146-150">Skype voor bedrijven online beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b146-150">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0b146-151">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b146-151">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0b146-152">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b146-152">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
