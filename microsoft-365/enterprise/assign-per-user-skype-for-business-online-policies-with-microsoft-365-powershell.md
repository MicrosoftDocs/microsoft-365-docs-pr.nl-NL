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
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Beleidsregels voor Skype voor bedrijven online toewijzen aan een gebruiker met PowerShell voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Het gebruik van PowerShell voor Microsoft 365 is een efficiënte manier om communicatie-instellingen per gebruiker toe te wijzen aan het beleid van Skype voor bedrijven online.
  
## <a name="prepare-to-run-the-powershell-commands"></a>Het uitvoeren van de PowerShell-opdrachten voorbereiden

Voer de volgende instructies uit om de opdrachten uit te voeren (u kunt de stappen die u al hebt voltooid overslaan):
  
1. Download en installeer de [connector module van Skype voor bedrijven online](https://www.microsoft.com/download/details.aspx?id=39366).
    
2. Open een Windows PowerShell-opdrachtprompt en voer de volgende opdrachten uit: 
    
```powershell
Import-Module LyncOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

Voer uw beheerdersaccount naam en wachtwoord voor Skype voor bedrijven online in wanneer hierom wordt gevraagd.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Instellingen voor externe communicatie voor een gebruikersaccount bijwerken

Stel dat u de instellingen voor externe communicatie voor een gebruikersaccount wilt wijzigen. U wilt bijvoorbeeld het voor de communicatie met federatieve gebruikers toestaan (EnableFederationAccess is gelijk aan waar), maar niet met Windows Live-gebruikers (EnablePublicCloudAccess is gelijk aan onwaar). Hiervoor moet u twee dingen doen:
  
1. Zoek een extern toegangsbeleid dat aan de criteria voldoet.
    
2. Wijs dit externe toegangsbeleid toe aan Alex.
    
Hoe bepaal ik welk externe toegangsbeleid moet worden toegewezen aan een Alex? Met de volgende opdracht worden alle externe toegangs beleidsregels geretourneerd waarbij EnableFederationAccess is ingesteld op waar en EnablePublicCloudAccess is ingesteld op ONWAAR:
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

Als u een aangepaste instantie van ExternalAccessPolicy hebt gemaakt, wordt door die opdracht één beleid geretourneerd dat voldoet aan de criteria (FederationOnly). Hier ziet u een voorbeeld:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Nu u weet welk beleid moet worden toegewezen aan het Alex, kunnen we dit beleid toewijzen met behulp van de cmdlet [Grant-CsExternalAccessPolicy](https://go.microsoft.com/fwlink/?LinkId=523974) . Hier ziet u een voorbeeld:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Het toewijzen van een beleid is tamelijk simpel: u geeft simpelweg de identiteit van de gebruiker op en de naam van het beleid dat u wilt toewijzen. 
  
En wanneer het gaat om beleidsregels en beleidstoewijzingen, kunt u niet beperkt werken met gebruikersaccounts één keer. Stel dat u een lijst met alle gebruikers wilt hebben die kunnen communiceren met federatieve partners en met Windows Live-gebruikers. U weet al dat aan deze gebruikers het externe beleid voor gebruikers toegang FederationAndPICDefault. Aangezien we weten dat u een lijst met al deze gebruikers kunt weergeven, voert u één eenvoudige opdracht uit. Dit is de opdracht:
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

Met andere woorden: Toon ons alle gebruikers waar de eigenschap ExternalAccessPolicy is ingesteld op FederationAndPICDefault. (En als u de hoeveelheid gegevens die op het scherm wordt weergegeven wilt beperken, gebruikt u de cmdlet select-object om de weergave van de gebruikersnaam weer te geven.) 
  
Als u al uw gebruikersaccounts wilt configureren voor gebruik van dit beleid, gebruikt u deze opdracht:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

Deze opdracht maakt gebruik van Get-CsOnlineUser om een verzameling te retourneren van alle gebruikers die zijn ingeschakeld voor Lync, en stuurt vervolgens al die informatie naar Grant-CsExternalAccessPolicy, waarmee het FederationAndPICDefault-beleid wordt toegewezen aan elke gebruiker in de verzameling.
  
Voorbeeld van een ander voorbeeld hebt u het FederationAndPICDefault-beleid eerder toegewezen en bent u van gedachten veranderd, en zou u ze wilt laten beheren door het globale externe toegangsbeleid. U kunt het globale beleid niet expliciet aan iedereen toewijzen. In plaats daarvan wordt het globale beleid gebruikt voor een bepaalde gebruiker als het beleid voor de gebruiker niet is toegewezen aan deze gebruiker. En als we willen dat de instelling wordt beheerd door het globale beleid, moet u dit beleid voor gebruikers die eerder aan de gebruiker zijn toegewezen,  *intrekken*  . Hier ziet u een voorbeeld van een opdracht:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Met deze opdracht stelt u de naam in van het externe toegangsbeleid dat is toegewezen aan Alex met een null-waarde ($Null). Null betekent ' niets '. Er worden dus geen beleid voor externe toegang toegewezen aan Alex. Wanneer er geen extern toegangsbeleid aan een gebruiker is toegewezen, wordt die gebruiker dan beheerd door het globale beleid.
  

## <a name="managing-large-numbers-of-users"></a>Grote aantallen gebruikers beheren

Als u een groot aantal gebruikers wilt beheren (1000 of meer), moet u de opdrachten batchgewijs batchiseren via een scriptblok met de cmdlet [invoke-opdracht](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7) .  In vorige voorbeelden moet de verbinding telkens wanneer een cmdlet wordt uitgevoerd, worden ingesteld en wordt het resultaat weergegeven voordat u het bericht verzendt.  Wanneer u een scriptblok gebruikt, kunt u hiermee de cmdlets extern uitvoeren en de gegevens terug verzenden. 

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

Met deze optie worden 500-gebruikers tegelijk gezocht die geen clientbeleid hebben. Het beleid voor de client ' ClientPolicyNoIMURL ' en het externe toegangsbeleid ' FederationAndPicDefault ' wordt toegekend. De resultaten worden batchgewijs omgezet in groepen van 50 en elke batch van 50 wordt vervolgens naar de externe computer verzonden.
  
## <a name="see-also"></a>Zie ook

[Skype voor bedrijven online beheren met PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
