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
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Een onlinebeleid Skype voor Bedrijven per gebruiker toewijzen met PowerShell voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

PowerShell gebruiken voor Microsoft 365 is een efficiënte manier om communicatie-instellingen per gebruiker toe te wijzen met Skype voor Bedrijven Online-beleid.
  
## <a name="prepare-to-run-the-powershell-commands"></a>De PowerShell-opdrachten voorbereiden

Gebruik deze instructies om de opdrachten uit te voeren (sla de stappen over die u al hebt voltooid):
  
  > [!Note]
   > Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module. Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.

1. Installeer de [Teams PowerShell-module](/microsoftteams/teams-powershell-install).
    
2. Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit: 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   Wanneer u hier om wordt gevraagd, voert u Skype voor Bedrijven naam en wachtwoord van uw onlinebeheerdersaccount in.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Externe communicatie-instellingen voor een gebruikersaccount bijwerken

Stel dat u instellingen voor externe communicatie in een gebruikersaccount wilt wijzigen. U wilt bijvoorbeeld toestaan dat Alex communiceert met federatieve gebruikers (EnableFederationAccess is gelijk aan Waar), maar niet met Windows Live-gebruikers (EnablePublicCloudAccess is gelijk aan Onwaar). Om dat te doen, moet u twee dingen doen:
  
1. Zoek een beleid voor externe toegang dat voldoet aan onze criteria.
    
2. Wijs dat beleid voor externe toegang toe aan Alex.
    
Hoe bepaalt u welk beleid voor externe toegang u Alex wilt toewijzen? De volgende opdracht retourneert alle beleidsregels voor externe toegang waarin EnableFederationAccess is ingesteld op Waar en EnablePublicCloudAccess is ingesteld op Onwaar:
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

Tenzij u aangepaste exemplaren van ExternalAccessPolicy hebt gemaakt, retourneert deze opdracht één beleid dat voldoet aan onze criteria (FederationOnly). Hier is een voorbeeld:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Nu u weet welk beleid aan Alex moet worden toegewezen, kunnen we dat beleid toewijzen met behulp van de [cmdlet Grant-CsExternalAccessPolicy.](/powershell/module/skype/Get-CsExternalAccessPolicy) Hier is een voorbeeld:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Het toewijzen van een beleid is vrij eenvoudig: u geeft alleen de identiteit van de gebruiker op en de naam van het beleid dat moet worden toegewezen. 
  
En als het gaat om beleid en beleidstoewijzingen, kunt u niet alleen één keer met gebruikersaccounts werken. Stel dat u een lijst nodig hebt met alle gebruikers die mogen communiceren met federatieve partners en met Windows Live-gebruikers. We weten al dat aan deze gebruikers het beleid voor externe gebruikerstoegang FederationAndPICDefault is toegewezen. Omdat we dat weten, kunt u een lijst met al die gebruikers weergeven door één eenvoudige opdracht uit te voeren. Hier is de opdracht:
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

Met andere woorden, laat ons alle gebruikers zien waar de eigenschap ExternalAccessPolicy is ingesteld op FederationAndPICDefault. (En als u de hoeveelheid informatie op het scherm wilt beperken, gebruikt u de cmdlet Select-Object om alleen de weergavenaam van elke gebruiker weer te geven.) 
  
Als u al onze gebruikersaccounts wilt configureren om hetzelfde beleid te gebruiken, gebruikt u deze opdracht:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

Deze opdracht gebruikt Get-CsOnlineUser om een verzameling van alle gebruikers te retourneren die zijn ingeschakeld voor Lync en stuurt vervolgens al deze informatie naar Grant-CsExternalAccessPolicy, waarmee het FederationAndPICDefault-beleid aan elke gebruiker in de verzameling wordt toegewezen.
  
Stel dat u Alex eerder het FederationAndPICDefault-beleid hebt toegewezen en nu bent u van gedachten veranderd en wilt u dat hij wordt beheerd door het globale beleid voor externe toegang. U kunt het globale beleid niet expliciet aan iemand toewijzen. In plaats daarvan wordt het algemene beleid voor een bepaalde gebruiker gebruikt als er geen beleid per gebruiker aan die gebruiker is toegewezen. Daarom, als we willen dat Alex wordt beheerd  door het globale beleid, moet u een beleid per gebruiker dat eerder aan hem is toegewezen, niet toewijzen. Hier is een voorbeeldopdracht:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Met deze opdracht wordt de naam van het beleid voor externe toegang dat aan Alex is toegewezen, ingedeeld in een null-waarde ($Null). Null betekent 'niets'. Met andere woorden, er is geen beleid voor externe toegang toegewezen aan Alex. Als er geen beleid voor externe toegang is toegewezen aan een gebruiker, wordt deze gebruiker vervolgens beheerd door het globale beleid.
  

## <a name="managing-large-numbers-of-users"></a>Grote aantallen gebruikers beheren

Als u grote aantallen gebruikers (1000 of meer) wilt beheren, moet u de opdrachten batcheren via een scriptblok met de cmdlet [Invoke-Command.](/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7)  In eerdere voorbeelden moet elke keer dat een cmdlet wordt uitgevoerd, de oproep worden ingesteld en vervolgens wachten op het resultaat voordat u deze terug verstuurt.  Wanneer u een scriptblok gebruikt, kunnen de cmdlets op afstand worden uitgevoerd en de gegevens terugsturen wanneer ze zijn voltooid. 

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

Hier vindt u 500 gebruikers tegelijk die geen clientbeleid hebben. De klant krijgt het clientbeleid 'ClientPolicyNoIMURL' en het beleid voor externe toegang 'FederationAndPicDefault'. De resultaten worden in groepen van 50 batched en elke batch van 50 wordt vervolgens naar de externe computer verzonden.
  
## <a name="see-also"></a>Zie ook

[Skype voor Bedrijven Online beheren met PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)