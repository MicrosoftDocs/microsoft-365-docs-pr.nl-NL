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
description: 'Overzicht: Gebruik PowerShell om de eigenschappen van uw gebruikersaccount van Skype voor Bedrijven Online te beheren met beleidsregels.'
ms.openlocfilehash: ca945bc05e76525b4b2df6fb0b982a8468d87810
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515050"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u veel eigenschappen van gebruikersaccounts voor Skype voor Bedrijven Online wilt beheren, moet u deze opgeven als eigenschappen van beleid met PowerShell voor Microsoft 365.
  
## <a name="before-you-begin"></a>Voordat u begint

Gebruik deze instructies om de opdrachten uit te voeren (sla de stappen over die u al hebt voltooid):

  > [!Note]
  > Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module. Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.

1. Installeer de [Teams PowerShell-module.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   Wanneer u daarom wordt gevraagd, voert u de naam en het wachtwoord van uw beheerdersaccount voor Skype voor Bedrijven Online in.
    
## <a name="manage-user-account-policies"></a>Beleid voor gebruikersaccounts beheren

Veel eigenschappen van gebruikersaccounts van Skype voor Bedrijven Online worden geconfigureerd op basis van beleidsregels. Beleidsregels zijn verzamelingen van instellingen die kunnen worden toegepast op een of meer gebruikers. Als u wilt weten hoe een beleid is geconfigureerd, kunt u deze voorbeeldopdracht uitvoeren voor het federationAndPICDefault-beleid:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

U moet op zijn beurt weer iets terug krijgen dat er ongeveer zo uit ziet:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

In dit voorbeeld bepalen de waarden in dit beleid wat een gebruik al dan niet kan doen bij het communiceren met federatief gebruikers. De eigenschap EnableOutsideAccess moet bijvoorbeeld zijn ingesteld op Waar als een gebruiker wil kunnen communiceren met personen buiten de organisatie. Deze eigenschap wordt niet weergegeven in het Microsoft 365-beheercentrum. In plaats daarvan wordt de eigenschap automatisch ingesteld op Waar of Onwaar op basis van de andere selecties die u maakt. De andere twee eigenschappen die interessant zijn, zijn:
  
- **EnableFederationAccess** geeft aan of de gebruiker kan communiceren met personen van federatiele domeinen.
    
- **Met EnablePublicCloudAccess** wordt aangegeven of de gebruiker kan communiceren met Windows Live-gebruikers.
    
Daarom wijzigt u niet rechtstreeks federatie-gerelateerde eigenschappen voor gebruikersaccounts (bijvoorbeeld **Set-CsUser -EnableFederationAccess $True).** In plaats daarvan wijst u een account een beleid voor externe toegang toe dat de gewenste eigenschapswaarden vooraf heeft geconfigureerd. Als we willen dat een gebruiker kan communiceren met federatieve gebruikers en met Windows Live-gebruikers, moet aan dat gebruikersaccount een beleid worden toegewezen waarmee deze typen communicatie worden toestaat.
  
Als u wilt weten of iemand kan communiceren met gebruikers van buiten de organisatie, moet u het volgende doen:
  
- Bepaal welk beleid voor externe toegang aan die gebruiker is toegewezen.
    
- Bepaal welke mogelijkheden wel of niet zijn toegestaan door dat beleid.
    
U kunt dit bijvoorbeeld doen met deze opdracht:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Met deze opdracht wordt het beleid gevonden dat is toegewezen aan de gebruiker en worden de mogelijkheden gevonden die binnen dat beleid zijn ingeschakeld of uitgeschakeld.
  
Zie de cmdlets voor het beheren van beleidsregels van Skype voor Bedrijven Online met PowerShell:

- [Clientbeleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Mobiel beleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Beleid voor online voicemail](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Spraakrouteringsbeleid](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Een skype voor Bedrijven Online-kiesplan is een beleid in alles behalve de naam. De naam 'kiesplan' is gekozen in plaats van 'kiesbeleid' om compatibiliteit met eerdere nummers te bieden met Office Communications Server en Exchange. 
  
Als u bijvoorbeeld alle spraakbeleidsregels wilt bekijken die beschikbaar zijn voor uw gebruik, kunt u deze opdracht uitvoeren:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Dit retourneert een lijst met alle spraakbeleidsregels die voor u beschikbaar zijn. Houd er echter rekening mee dat niet alle beleidsregels aan alle gebruikers kunnen worden toegewezen. Dit komt door verschillende beperkingen met betrekking tot licenties en geografische locatie. (De zogeheten[gebruikslocatie](https://msdn.microsoft.com/library/azure/dn194136.aspx).") Als u wilt weten wat het beleid voor externe toegang is en wat het conferencing-beleid is dat aan een bepaalde gebruiker kan worden toegewezen, gebruikt u de volgende opdrachten: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

De parameter ApplicableTo beperkt de geretourneerde gegevens tot beleid dat kan worden toegewezen aan de opgegeven gebruiker (bijvoorbeeld Alex Darrow). Afhankelijk van de beperkingen voor de gebruiks- en gebruikslocatie, kan dit een subset van alle beschikbare beleidsregels vertegenwoordigen. 
  
In sommige gevallen worden eigenschappen van beleid niet gebruikt met Microsoft 365, terwijl andere eigenschappen alleen kunnen worden beheerd door personeel van de Microsoft-ondersteuning. 
  
Met Skype voor Bedrijven Online moeten gebruikers worden beheerd door een beleid van een bepaalde soort. Als een geldige beleidsgerelateerde eigenschap leeg is, betekent dit dat de gebruiker in kwestie wordt beheerd door een globaal beleid. Dit is een beleid dat automatisch wordt toegepast op een gebruiker, tenzij aan hem of haar specifiek een beleid per gebruiker wordt toegewezen. Aangezien er geen clientbeleid wordt vermeld voor een gebruikersaccount, wordt het beheerd door het algemene beleid. U kunt het globale clientbeleid bepalen met deze opdracht:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Zie ook

[Skype voor Bedrijven Online beheren met PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)

