---
title: Skype voor Bedrijven Online-beleidsregels per gebruiker toewijzen met PowerShell voor Microsoft 365
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
description: 'Overzicht: Gebruik PowerShell voor Microsoft 365 om communicatie-instellingen per gebruiker toe te wijzen met skype voor Bedrijven Online-beleidsregels.'
ms.openlocfilehash: 6ee237e5d2ee0c9f472f372a6aa66c9612336265
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514978"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a>Skype voor Bedrijven Online-beleidsregels per gebruiker toewijzen met PowerShell voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Het gebruik van PowerShell voor Microsoft 365 is een efficiënte manier om communicatie-instellingen per gebruiker toe te wijzen met beleidsregels van Skype voor Bedrijven Online.
  
## <a name="prepare-to-run-the-powershell-commands"></a>De PowerShell-opdrachten voorbereiden

Gebruik deze instructies om de opdrachten uit te voeren (sla de stappen over die u al hebt voltooid):
  
  > [!Note]
   > Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module. Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.

1. Installeer de [Teams PowerShell-module.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit: 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   Wanneer u daarom wordt gevraagd, voert u de naam en het wachtwoord van uw beheerdersaccount voor Skype voor Bedrijven Online in.
    
## <a name="updating-external-communication-settings-for-a-user-account"></a>Instellingen voor externe communicatie bijwerken voor een gebruikersaccount

Stel dat u instellingen voor externe communicatie van een gebruikersaccount wilt wijzigen. U wilt bijvoorbeeld toestaan dat Alex communiceert met federatieve gebruikers (EnableFederationAccess is gelijk aan Waar), maar niet met Windows Live-gebruikers (EnablePublicCloudAccess is gelijk aan False). U moet twee dingen doen:
  
1. Zoek een beleid voor externe toegang dat aan de criteria voldoet.
    
2. Wijs dat beleid voor externe toegang toe aan Alex.
    
Hoe bepaalt u welk beleid voor externe toegang Alex moet toewijzen? De volgende opdracht retourneert alle beleidsregels voor externe toegang waarbij EnableFederationAccess is ingesteld op Waar en EnablePublicCloudAccess is ingesteld op Onwaar:
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

Tenzij u aangepaste exemplaren van ExternalAccessPolicy hebt gemaakt, retourneert deze opdracht één beleid dat aan de criteria voldoet (FederationOnly). Hier is een voorbeeld:
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

Nu u weet welk beleid moet worden toegewezen aan Alex, kunnen we dat beleid toewijzen met behulp van de [cmdlet Grant-CsExternalAccessPolicy.](https://go.microsoft.com/fwlink/?LinkId=523974) Hier is een voorbeeld:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

Het toewijzen van een beleid is vrij eenvoudig: u geeft de identiteit van de gebruiker en de naam op van het beleid dat moet worden toegewezen. 
  
En als het gaat om beleid en beleidstoewijzingen, bent u niet beperkt tot het één voor één werken met gebruikersaccounts. U hebt bijvoorbeeld een lijst nodig met alle gebruikers die mogen communiceren met federatieve partners en met Windows Live-gebruikers. We weten al dat aan deze gebruikers het toegangsbeleid voor externe gebruikers FederationAndPICDefault is toegewezen. Omdat we dat weten, kunt u een lijst met al deze gebruikers weergeven door één eenvoudige opdracht uit te voeren. Dit is de opdracht:
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

Met andere woorden, laat ons alle gebruikers zien waar de eigenschap ExternalAccessPolicy is ingesteld op FederationAndPICDefault. (En als u de hoeveelheid informatie op het scherm wilt beperken, gebruikt u de cmdlet Select-Object om alleen de weergavenaam van elke gebruiker weer te geven.) 
  
Als u al onze gebruikersaccounts wilt configureren voor hetzelfde beleid, gebruikt u deze opdracht:
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

Met deze opdracht wordt Get-CsOnlineUser gebruikt om een verzameling gebruikers te retourneren voor wie Lync is ingeschakeld, waarna al deze gegevens worden doorverbonden naar Grant-CsExternalAccessPolicy, waarmee het FederationAndPICDefault-beleid wordt toegewezen aan elke gebruiker in de verzameling.
  
Stel dat u eerder het beleid FederationAndPICDefault hebt toegewezen aan Alex en nu bent u van gedachten veranderd en wilt u dat hij wordt beheerd door het globale beleid voor externe toegang. U kunt het globale beleid niet expliciet aan iemand toewijzen. In plaats daarvan wordt het algemene beleid voor een bepaalde gebruiker gebruikt als er geen beleid per gebruiker aan die gebruiker is toegewezen. Als we dus willen dat Alex wordt beheerd door  het globale beleid, moet u beleid per gebruiker, dat eerder aan hem is toegewezen, in de weg staan. Hier is een voorbeeldopdracht:
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

Met deze opdracht wordt de naam van het beleid voor externe toegang die aan Alex is toegewezen, op een null-waarde ($Null). Null betekent 'niets'. Met andere woorden, er wordt geen beleid voor externe toegang toegewezen aan Alex. Als er geen beleid voor externe toegang aan een gebruiker is toegewezen, wordt die gebruiker vervolgens beheerd door het globale beleid.
  

## <a name="managing-large-numbers-of-users"></a>Grote aantallen gebruikers beheren

Als u een groot aantal gebruikers (meer dan 1000) wilt beheren, moet u de opdrachten batcheren via een scriptblok met behulp van de [Invoke-Command-cmdlet.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-7)  In eerdere voorbeelden: telkens als een cmdlet wordt uitgevoerd, moet de oproep worden ingesteld en vervolgens worden gewacht op het resultaat voordat de cmdlet terug wordt verzonden.  Als u een scriptblok gebruikt, kunnen de cmdlets op afstand worden uitgevoerd en de gegevens daarna weer terugsturen. 

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

Hiermee vindt u 500 gebruikers tegelijk die geen clientbeleid hebben. Het clientbeleid 'ClientPolicyNoIMURL' en het beleid voor externe toegang 'FederationAndPicDefault' worden aan hen toegekend. De resultaten worden batched in groepen van 50 en elke batch van 50 wordt vervolgens verzonden naar de externe computer.
  
## <a name="see-also"></a>Zie ook

[Skype voor Bedrijven Online beheren met PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)
