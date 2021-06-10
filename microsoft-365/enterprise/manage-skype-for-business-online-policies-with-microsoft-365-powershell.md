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
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Beleidsregels voor Skype voor Bedrijven Online beheren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als u veel eigenschappen van gebruikersaccounts voor Skype voor Bedrijven Online wilt beheren, moet u deze opgeven als eigenschappen van beleidsregels met PowerShell voor Microsoft 365.
  
## <a name="before-you-begin"></a>Voordat u begint

Gebruik deze instructies om de opdrachten uit te voeren (sla de stappen over die u al hebt voltooid):

  > [!Note]
  > Skype voor Bedrijven Online-connector maakt momenteel deel uit van de nieuwste Teams PowerShell-module. Als u de meest recente openbare versie van Teams PowerShell gebruikt, hoeft u de Skype voor Bedrijven Online-connector niet te installeren.

1. Installeer de [Teams PowerShell-module](/microsoftteams/teams-powershell-install).
    
2. Open een opdrachtprompt van Windows PowerShell en voer de volgende opdrachten uit: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

   Wanneer u hier om wordt gevraagd, voert u Skype voor Bedrijven naam en wachtwoord van uw onlinebeheerdersaccount in.
    
## <a name="manage-user-account-policies"></a>Beleidsregels voor gebruikersaccounts beheren

Veel Skype voor Bedrijven eigenschappen van onlinegebruikersaccounts worden geconfigureerd met behulp van beleidsregels. Beleidsregels zijn gewoon verzamelingen met instellingen die kunnen worden toegepast op een of meer gebruikers. Als u wilt bekijken hoe het beleid is geconfigureerd, kunt u deze voorbeeldopdracht uitvoeren voor het FederationAndPICDefault-beleid:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

Op zijn beurt moet u iets dergelijks als dit terug krijgen:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

In dit voorbeeld bepalen de waarden in dit beleid wat een gebruik wel of niet kan doen als het gaat om communiceren met federatief gebruikers. De eigenschap EnableOutsideAccess moet bijvoorbeeld zijn ingesteld op Waar zodat een gebruiker kan communiceren met personen buiten de organisatie. Houd er rekening mee dat deze eigenschap niet wordt weergegeven in het Microsoft 365 beheercentrum. In plaats daarvan wordt de eigenschap automatisch ingesteld op Waar of Onwaar op basis van de andere selecties die u maakt. De andere twee eigenschappen van belang zijn:
  
- **EnableFederationAccess** geeft aan of de gebruiker kan communiceren met personen uit federatief domeinen.
    
- **EnablePublicCloudAccess** geeft aan of de gebruiker kan communiceren met Windows Live-gebruikers.
    
Daarom wijzigt u niet rechtstreeks federatie-gerelateerde eigenschappen op gebruikersaccounts (bijvoorbeeld **Set-CsUser -EnableFederationAccess $True).** In plaats daarvan wijst u een account een beleid voor externe toegang toe dat de gewenste eigenschapswaarden vooraf heeft geconfigureerd. Als we willen dat een gebruiker kan communiceren met federatieve gebruikers en met Windows Live-gebruikers, moet aan dat gebruikersaccount een beleid worden toegewezen waarmee deze typen communicatie mogelijk zijn.
  
Als u wilt weten of iemand kan communiceren met gebruikers van buiten de organisatie, moet u het volgende doen:
  
- Bepaal welk beleid voor externe toegang aan die gebruiker is toegewezen.
    
- Bepaal welke mogelijkheden wel of niet zijn toegestaan in dat beleid.
    
U kunt dit bijvoorbeeld doen met deze opdracht:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Met deze opdracht wordt het beleid gevonden dat aan de gebruiker is toegewezen en worden vervolgens de mogelijkheden gevonden die in dat beleid zijn ingeschakeld of uitgeschakeld.
  
Zie de cmdlets voor Skype voor Bedrijven onlinebeleid beheren met PowerShell:

- [Clientbeleid](/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Conferencingbeleid](/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Mobiel beleid](/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Beleid voor online voicemail](/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [Beleid voor spraakroutering](/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Een Skype voor Bedrijven Online-kiesplan is in alle opzichten een beleid, behalve de naam. De naam 'kiesplan' is gekozen in plaats van bijvoorbeeld 'kiesbeleid' om achterwaartse compatibiliteit te bieden met Office Communications Server en met Exchange. 
  
Als u bijvoorbeeld alle spraakbeleidsregels wilt bekijken die beschikbaar zijn voor uw gebruik, voer dan deze opdracht uit:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Dit geeft als return een lijst met alle spraakbeleidsregels die beschikbaar zijn voor u. Houd er echter rekening mee dat niet alle beleidsregels aan alle gebruikers kunnen worden toegewezen. Dit komt door verschillende beperkingen met betrekking tot licenties en geografische locatie. (De zogenaamde "[gebruikslocatie](/previous-versions/azure/dn194136(v=azure.100)).") Als u wilt weten wat het beleid voor externe toegang is en welke beleidsregels voor conferencing aan een bepaalde gebruiker kunnen worden toegewezen, gebruikt u opdrachten die vergelijkbaar zijn met deze: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

De parameter ApplicableTo beperkt de geretourneerde gegevens tot beleid dat kan worden toegewezen aan de opgegeven gebruiker (bijvoorbeeld Alex Darrow). Afhankelijk van licentie- en gebruikslocatiebeperkingen kan dit een subset van alle beschikbare beleidsregels vertegenwoordigen. 
  
In sommige gevallen worden eigenschappen van beleid niet gebruikt met Microsoft 365, terwijl andere alleen kunnen worden beheerd door ondersteuningsmedewerkers van Microsoft. 
  
Met Skype voor Bedrijven Online moeten gebruikers worden beheerd door een beleid van een bepaalde soort. Als een geldige beleidsgerelateerde eigenschap leeg is, betekent dit dat de gebruiker in kwestie wordt beheerd door een globaal beleid. Dit is een beleid dat automatisch wordt toegepast op een gebruiker, tenzij aan hem of haar specifiek een beleid per gebruiker is toegewezen. Omdat er geen clientbeleid wordt weergegeven voor een gebruikersaccount, wordt het beheerd door het algemene beleid. Met deze opdracht kunt u het globale clientbeleid bepalen:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Zie ook

[Skype voor Bedrijven Online beheren met PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Aan de slag met PowerShell voor Microsoft 365](getting-started-with-microsoft-365-powershell.md)