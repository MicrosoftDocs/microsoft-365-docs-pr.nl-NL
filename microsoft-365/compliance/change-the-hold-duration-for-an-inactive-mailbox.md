---
title: De duur van bewaring van een inactief postvak wijzigen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Nadat een Office 365 inactief is gemaakt, wijzigt u de duur van de bewaring of Office 365 bewaarbeleid die is toegewezen aan het inactieve postvak.
ms.openlocfilehash: 49d133c64763cee12cb26e27d372a16ba4ad7e94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161920"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>De duur van bewaring van een inactief postvak wijzigen

Een inactief postvak wordt gebruikt om de e-mail van een voormalige werknemer te behouden nadat hij of zij uw organisatie heeft verlaat. Een postvak wordt inactief wanneer een bewaring voor rechtszaken, een In-Place bewaring, een bewaarbeleid voor Microsoft 365 of een bewaring die is gekoppeld aan een eDiscovery-zaak in het postvak wordt geplaatst en het bijbehorende gebruikersaccount wordt verwijderd. De inhoud van een inactief postvak blijft behouden gedurende de duur van de wacht die in het postvak is geplaatst voordat het inactief werd gemaakt. De duur van de wachttijd bepaalt hoe lang items in de map Herstelbare items worden gehouden. Wanneer de duur van de wachttijd voor een item in de map Herstelbare items verloopt, wordt het item definitief verwijderd (verwijderd) uit het inactieve postvak. Nadat een postvak inactief is gemaakt, kunt u de duur van de bewaring wijzigen of Microsoft 365 bewaarbeleid dat is toegewezen aan het inactieve postvak.
  
> [!IMPORTANT]
> Terwijl we op verschillende manieren blijven investeren om postvakinhoud te behouden, kondigen we de uittreding aan van In-Place Holds in het Exchange beheercentrum. Dit betekent dat u een inactief postvak moet maken met Microsoft 365 bewaarbeleid. Vanaf 1 april 2020 kunt u geen nieuwe In-Place in Exchange Online. Maar u kunt de duur van de wachttijd van een In-Place in een inactief postvak wijzigen. Vanaf 1 juli 2020 kunt u de duur van de wachttijd echter niet wijzigen. U kunt alleen een inactief postvak verwijderen door de In-Place verwijderen. Bestaande inactieve postvakken die in de wacht In-Place blijven behouden totdat de wacht wordt verwijderd. Zie Retirement of legacy eDiscovery tools (Oude eDiscovery-hulpprogramma's) voor meer informatie over het In-Place van [eDiscovery-functies.](legacy-ediscovery-retirement.md)
  
## <a name="connect-to-powershell"></a>Verbinding maken naar PowerShell

- U moet de Exchange Online PowerShell gebruiken om de duur van de duur van een geschil in een inactief postvak te wijzigen. U kunt het beheercentrum Exchange (EAC) niet gebruiken. Maar u kunt de Exchange Online PowerShell of de EAC gebruiken om de duur van de wachttijd voor een In-Place wijzigen. U kunt het beveiligings- en compliancecentrum of het Beveiligings- & Compliancecentrum PowerShell gebruiken om de duur van de bewaring voor een Microsoft 365 te wijzigen.
    
- Zie een van de volgende onderwerpen Exchange Online Verbinding maken met PowerShell of &-compliancecentrum PowerShell:
    
  - [Verbinding maken powershell Exchange Online gebruiken](/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [Verbinding maken beveiligingscentrum & PowerShell](/powershell/exchange/connect-to-scc-powershell)
    
- Aan eDiscovery-zaken gekoppelde wacht houdt oneindig vast, wat betekent dat er geen duur van de wacht kan worden gewijzigd. Items worden voor altijd of totdat de wacht wordt verwijderd en het inactieve postvak wordt verwijderd.
    
- Zie Inactieve postvakken in Microsoft 365 voor meer informatie over inactieve [postvakken.](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Stap 1: De inboxen in een inactief postvak identificeren

Omdat verschillende typen bewaringen of een of meer Microsoft 365 bewaarbeleid mogelijk in een inactief postvak worden geplaatst, is de eerste stap het identificeren van de bewaringen in een inactief postvak.
  
Voer de volgende opdracht uit in Exchange Online PowerShell om de wachtgegevens weer te geven voor alle inactieve postvakken in uw organisatie.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

De waarde van **Waar** voor de **eigenschap LitigationHoldEnabled** geeft aan dat het inactieve postvak zich in de procesvaste procedure houdt. Als een In-Place bewaringsbeleid, eDiscovery-bewaring of Microsoft 365-bewaarbeleid op een inactief postvak wordt geplaatst, wordt een GUID voor het bewaar- of bewaarbeleid weergegeven als de waarde voor de eigenschap **InPlaceHolds.** In het volgende ziet u bijvoorbeeld resultaten voor vijf inactieve postvakken. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

In de volgende tabel worden de vijf verschillende typen in de wacht gezet die zijn gebruikt om elk postvak inactief te maken.
  
|**Inactief postvak**|**Type wacht houden**|**De wacht in het inactieve postvak identificeren**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Proces in de wacht zetten  <br/> |De  *eigenschap LitigationHoldEnabled*  is ingesteld op  `True` .  <br/> |
|Pilar Pinilla  <br/> |In-Place Hold  <br/> |De  *eigenschap InPlaceHolds*  bevat de GUID van de In-Place Hold die in het inactieve postvak is geplaatst. U kunt zien dat dit een In-Place Omdat de id niet begint met een voorvoegsel.  <br/> U kunt de opdracht in Exchange Online PowerShell gebruiken om informatie te krijgen over de `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` In-Place Inactief postvak in de wacht houden.  <br/> |
|Mario Necaise  <br/> |Organisatiebrede Microsoft 365 bewaarbeleid in het beveiligings- & compliancecentrum  <br/> |De  *eigenschap InPlaceHolds*  is leeg. Dit geeft aan dat een of meer organisatiebrede of (Exchange- of Microsoft 365 bewaarbeleid wordt toegepast op het inactieve postvak. In dit geval kunt u de opdracht uitvoeren in Exchange Online PowerShell om een lijst te krijgen met de GUID's voor het `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Microsoft 365 bewaarbeleid. De GUID voor bewaarbeleid voor de hele organisatie die wordt toegepast op Exchange postvakken beginnen met het `mbx` voorvoegsel, bijvoorbeeld `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> <br/>Als u de identiteit wilt Microsoft 365 het bewaarbeleid dat is toegepast op het inactieve postvak, moet u de volgende opdracht uitvoeren in Security & Compliance Center PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Microsoft 365 bewaarbeleid in het Beveiligings- & compliancecentrum toegepast op specifieke postvakken  <br/> |De *eigenschap InPlaceHolds* bevat de GUID van het Microsoft 365 bewaarbeleid dat is toegepast op het inactieve postvak. U kunt zien dat dit een bewaarbeleid is dat is toegepast op specifieke postvakken, omdat de GUID begint met het  `mbx` voorvoegsel. Als de GUID van het bewaarbeleid dat is toegepast op het inactieve postvak is gestart met het voorvoegsel, geeft dit aan dat het bewaarbeleid wordt toegepast op Skype voor Bedrijven `skp` gesprekken.  <br/><br/> Als u de identiteit wilt Microsoft 365 het bewaarbeleid dat is toegepast op het inactieve postvak, moet u de volgende opdracht uitvoeren in Security & Compliance Center PowerShell.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Verwijder het voorvoegsel  `mbx` of  `skp` het voorvoegsel wanneer u deze opdracht uit te voeren.  <br/> |
|Abraham McMahon  <br/> |eDiscovery case hold in the Security & Compliance Center  <br/> |De  *eigenschap InPlaceHolds*  bevat de GUID van de eDiscovery-case hold die in het inactieve postvak wordt geplaatst. U kunt zien dat dit een eDiscovery-zaak is, omdat de GUID begint met het  `UniH` voorvoegsel.  <br/> U kunt de cmdlet in Security & Compliance Center PowerShell gebruiken om informatie te krijgen over de eDiscovery-zaak waar de wacht in het inactieve postvak aan  `Get-CaseHoldPolicy` is gekoppeld. U kunt bijvoorbeeld de opdracht uitvoeren om de naam weer te geven van de case hold in  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` het inactieve postvak. Zorg ervoor dat u het  `UniH` voorvoegsel verwijdert wanneer u deze opdracht uit te voeren.  <br/><br/> Voer de volgende opdrachten uit om de eDiscovery-zaak te identiteiten die aan de inactieve postvak zijn gekoppeld.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Opmerking:** We raden u af om eDiscovery-postvakken te gebruiken voor inactieve postvakken. Dat komt omdat eDiscovery-zaken zijn bedoeld voor specifieke, tijdgebonden zaken die betrekking hebben op een juridisch probleem. Op een gegeven moment eindigt een juridische zaak waarschijnlijk en worden de aan de zaak gekoppelde aan de zaak ingetrokken en wordt de eDiscovery-zaak gesloten (of verwijderd). Als een wacht in een inactief postvak is gekoppeld aan een eDiscovery-zaak en de wacht wordt vrijgegeven of de eDiscovery-zaak wordt gesloten of verwijderd, wordt het inactieve postvak definitief verwijderd. 

Zie Meer informatie over bewaarbeleid Microsoft 365 bewaarbeleid voor meer informatie over bewaarbeleid [en bewaarlabels.](retention.md)
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Stap 2: De duur van de wachttijd voor een inactief postvak wijzigen

Nadat u hebt bepaald welk type wacht in het inactieve postvak wordt geplaatst (en of er meerdere wachtvakken zijn), is de volgende stap het wijzigen van de duur van de wacht. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>De duur van een proces in de wacht houden wijzigen

U kunt deze optie als Exchange Online PowerShell gebruiken om de duur van de duur van een geschil te wijzigen die in een inactief postvak wordt geplaatst. U kunt het EAC niet gebruiken. Voer de volgende opdracht uit om de duur van de wacht te wijzigen. In dit voorbeeld wordt de duur van de wachtperiode gewijzigd in een onbeperkte periode.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

Het resultaat is dat items in het inactieve postvak voor onbepaalde tijd worden bewaard of totdat de wacht wordt verwijderd of de duur van de wachttijd wordt gewijzigd in een andere waarde.
  
> [!TIP]
> De beste manier om een inactief postvak te identificeren, is door de **distinguished name** of **Exchange GUID-waarde te** gebruiken. Als u een van deze waarden gebruikt, voorkomt u dat per ongeluk het verkeerde postvak wordt opgegeven. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>De duur van een In-Place wijzigen

 In-Place Zijn ingetrokken en kunnen niet meer worden gewijzigd. Als op een inactief postvak een In-Place hold is toegepast, kunt u de duur van de wacht niet wijzigen. U kunt de In-Place alleen verwijderen, wat resulteert in het verwijderen van het inactieve postvak. Zie Een inactief postvak [verwijderen voor meer informatie.](delete-an-inactive-mailbox.md#remove-in-place-holds)
  
## <a name="more-information"></a>Meer informatie

- **Hoe wordt de duur van de wachttijd berekend voor een item in een inactief postvak?** De duur wordt berekend vanaf de oorspronkelijke datum waarop een postvakitem is ontvangen of gemaakt. 
    
- **Wat gebeurt er wanneer de duur van de wachttermijn verloopt?** Wanneer de duur van de wachttijd voor een postvakitem in de map Herstelbare items verloopt, wordt het item permanent verwijderd (verwijderd) uit het inactieve postvak. Als er geen duur is opgegeven voor de wacht in het inactieve postvak, worden items in de map Herstelbare items nooit verwijderd (tenzij de duur van de wacht voor het inactieve postvak wordt gewijzigd). 
    
- **Wordt een Exchange bewaarbeleid nog steeds verwerkt in inactieve postvakken?** Als een Exchange-bewaarbeleid (het beheer van berichtenrecords of mrm, functie in Exchange Online) is toegepast op een postvak toen het inactief werd gemaakt, worden het verwijderingsbeleid (bewaarlabels die zijn geconfigureerd met een bewaaractie Verwijderen) nog steeds verwerkt in het inactieve postvak.  Dit betekent dat items die zijn gemarkeerd met een verwijderingsbeleid, worden verplaatst naar de map Herstelbare items wanneer de bewaarperiode verloopt. Deze items worden vervolgens verwijderd uit het inactieve postvak wanneer de duur van de wachttijd voor een item verloopt. 
    
    Archiefbeleid (bewaarlabels die zijn geconfigureerd met een actie Voorarchiveren van **MoveToArchive)** die zijn opgenomen in het bewaarbeleid dat is toegewezen aan een inactief postvak, wordt daarentegen genegeerd. Dit betekent dat items in een inactief postvak die zijn gelabeld met een archiefbeleid, in het primaire postvak blijven wanneer de bewaarperiode verloopt. Ze worden niet verplaatst naar het archiefpostvak of naar de map Herstelbare items in het archiefpostvak. Omdat een gebruiker zich niet kan aanmelden bij een inactief postvak, is er geen reden om datacenterresources te gebruiken om archiefbeleid te verwerken. 

- **Voer de volgende opdrachten uit als u de nieuwe duur van de wachttijd voor een proces in de wacht wilt zetten** 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- **Net als gewone postvakken verwerkt de MFA (Managed Folder Assistant) ook inactieve postvakken.** In Exchange Online verwerkt de MFA postvakken ongeveer eenmaal per zeven dagen. Nadat u de duur van de wachtstand voor een inactief postvak hebt gewijzigd, kunt u de **cmdlet Start-ManagedFolderAssistant** gebruiken om de nieuwe duur van de wachtstand voor het inactieve postvak onmiddellijk te verwerken. Voer de volgende opdracht uit. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Als er veel wachtvakken in een inactief postvak worden geplaatst, worden niet alle wacht-GUID's weergegeven.** U kunt de volgende opdracht uitvoeren om de GUID's weer te geven voor alle in- en uitstalvakken (behalve Procesvoeringen) die in een inactief postvak zijn geplaatst. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```