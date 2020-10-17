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
description: 'Overzicht: PowerShell gebruiken voor het beheren van de eigenschappen van een gebruikersaccount van Skype voor bedrijven online met beleidsregels.'
ms.openlocfilehash: 20a75fa1c131f693fcf30d20477af5c9ee7aed35
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477039"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u een groot aantal eigenschappen van een gebruikersaccount voor Skype voor bedrijven online wilt beheren, moet u ze als eigenschappen van het beleid opgeven met PowerShell voor Microsoft 365.
  
## <a name="before-you-begin"></a>Voordat u begint

Voer de volgende instructies uit om de opdrachten uit te voeren (u kunt de stappen die u al hebt voltooid overslaan):

  > [!Note]
  > Skype voor bedrijven online connector maakt nu deel uit van de meest recente PowerShell-module van teams. Als u de meest recente versie van de openbare PowerShell-versie van PowerShell gebruikt, hoeft u de connector Skype voor bedrijven online niet te installeren.

1. Installeer de [PowerShell-module teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   Voer uw beheerdersaccount naam en wachtwoord voor Skype voor bedrijven online in wanneer hierom wordt gevraagd.
    
## <a name="manage-user-account-policies"></a>Beleidsregels voor gebruikersaccounts beheren

Veel eigenschappen van een gebruikersaccount van Skype voor bedrijven online worden geconfigureerd met behulp van beleid. Beleidsregels zijn simpelweg verzamelingen met instellingen die kunnen worden toegepast op een of meer gebruikers. Als u wilt bekijken hoe het beleid is geconfigureerd, kunt u dit voorbeeld-opdracht uitvoeren voor het FederationAndPICDefault-beleid:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

Op de beurt moet u iets op de volgende manier weergeven:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

In dit voorbeeld bepalen de waarden binnen dit beleid wat een gebruik of niet kan doen wanneer het gaat om communiceren met federatieve gebruikers. Als u bijvoorbeeld wilt dat een gebruiker kan communiceren met personen buiten de organisatie, moet de eigenschap EnableOutsideAccess zijn ingesteld op waar. Deze eigenschap wordt niet weergegeven in het Microsoft 365-Beheercentrum. In plaats daarvan wordt de eigenschap automatisch ingesteld op waar of onwaar, op basis van de andere selecties die u aanbrengt. De andere twee eigenschappen van belang zijn:
  
- **EnableFederationAccess** geeft aan of de gebruiker kan communiceren met mensen van federatieve domeinen.
    
- **EnablePublicCloudAccess** geeft aan of de gebruiker kan communiceren met Windows Live-gebruikers.
    
U kunt dus niet rechtstreeks Federatie gerelateerde eigenschappen wijzigen voor gebruikersaccounts (bijvoorbeeld **set-CsUser-EnableFederationAccess $True**). U kunt in plaats daarvan een extern toegangsbeleid toewijzen waarbij de gewenste eigenschapswaarden vooraf zijn geconfigureerd. Als u wilt dat een gebruiker kan communiceren met federatieve gebruikers en met Windows Live-gebruikers, moet aan die gebruikersaccount een beleid worden toegewezen dat de communicatie tussen deze typen toestaat.
  
Als u wilt weten of iemand met gebruikers van buiten de organisatie kan communiceren, moet u het volgende doen:
  
- Bepaal welk extern toegangsbeleid is toegewezen aan deze gebruiker.
    
- Bepalen welke mogelijkheden wel of niet zijn toegestaan door het beleid.
    
U kunt bijvoorbeeld de volgende opdracht gebruiken:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Met deze opdracht vindt u het beleid dat is toegewezen aan de gebruiker en vindt u vervolgens de functies die zijn ingeschakeld of uitgeschakeld binnen dat beleid.
  
Als u het beleid van Skype voor bedrijven online wilt beheren met PowerShell, raadpleegt u de cmdlets voor:

- [Client beleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Vergader beleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Mobiel beleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Online voicemail beleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Routeringsbeleid voor spraak](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Een Skype voor bedrijven online-Kies plan is voor elk opzicht een beleid met uitzondering van de naam. Voor de compatibiliteit met Office Communications Server en Exchange is de naam ' Kies plan ' in plaats van ' Kies beleid ' gekozen. 
  
Voer de volgende opdracht uit om alle voicemail beleidsregels te bekijken die voor uw gebruik beschikbaar zijn:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Hiermee wordt een lijst geretourneerd met alle voicemail beleidsregels die beschikbaar zijn voor u. Houd er rekening mee dat u niet alle beleidsregels aan alle gebruikers kunt toewijzen. Dit wordt veroorzaakt door verschillende beperkingen met betrekking tot licentieverlening en geografische ligging. (De zogenaamde[gebruikslocatie](https://msdn.microsoft.com/library/azure/dn194136.aspx)) Als u wilt weten hoe het beleid voor externe toegang en het beleid voor vergaderen dat aan een bepaalde gebruiker kan worden toegewezen, kunt u vinden in de volgende opdrachten: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

Met de ApplicableTo-parameter wordt de geretourneerde gegevens gelimiteerd aan beleidsregels die kunnen worden toegewezen aan de opgegeven gebruiker (bijvoorbeeld Alex Darrow). Afhankelijk van de beperkingen voor locatie van licentie en gebruik van een locatie, kunt u een subset van alle beschikbare beleidsregels vertegenwoordigen. 
  
In sommige gevallen worden de eigenschappen van beleidsregels niet gebruikt met Microsoft 365, terwijl andere personen de medewerkers van Microsoft ondersteunen. 
  
Met Skype voor bedrijven online dienen gebruikers een beleid van enige aard te beheren. Als een geldige eigenschap voor het beleid leeg is, betekent dit dat de aangevraagde gebruiker wordt beheerd door een algemeen beleid, dat een beleid is dat automatisch wordt toegepast op een gebruiker, tenzij hij of zij specifiek een beleid per gebruiker toewijst. Aangezien er geen clientbeleid wordt weergegeven voor een gebruikersaccount, wordt dit beheerd door het globale beleid. U kunt het beleid voor globale clients bepalen met de volgende opdracht:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Zie ook

[Skype voor Bedrijven Online beheren met PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

