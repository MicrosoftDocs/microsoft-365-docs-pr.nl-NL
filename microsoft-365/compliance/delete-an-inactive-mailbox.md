---
title: Een inactief postvak verwijderen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Wanneer u de inhoud van een inactief postvak niet meer Microsoft 365, kunt u het inactieve postvak definitief verwijderen.
ms.openlocfilehash: 077a71bfdd82721e0992e5d14073aa037b7cfd1b
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162864"
---
# <a name="delete-an-inactive-mailbox"></a>Een inactief postvak verwijderen

Een inactief postvak wordt gebruikt om de e-mail van een voormalige werknemer te behouden nadat deze uw organisatie heeft verlaten. Als u de inhoud van een inactief postvak niet meer wilt behouden, kunt u het inactieve postvak definitief verwijderen door de wacht te verwijderen. Het is ook mogelijk dat meerdere postvakken in een inactief postvak worden geplaatst. Een inactief postvak kan bijvoorbeeld worden geplaatst in de wacht voor rechtszaken en op een of meer In-Place In- In-Place. Daarnaast kan een bewaarbeleid (gemaakt in het beveiligings- en compliancecentrum in Office 365 of Microsoft 365) worden toegepast op het inactieve postvak. U moet alle bewaarbeleidsregels uit een inactief postvak verwijderen om het te verwijderen. Nadat u het bewaarbeleid hebt verwijderd, wordt het inactieve postvak gemarkeerd voor verwijdering en definitief verwijderd nadat het is verwerkt.
  
> [!IMPORTANT]
> Terwijl we op verschillende manieren blijven investeren om postvakinhoud te behouden, kondigen we de uittreding aan van In-Place Holds in het Exchange beheercentrum. Dit betekent dat u beleidsregels voor bewaring en bewaring van rechtszaken moet gebruiken om een inactief postvak te maken. Vanaf 1 juli 2020 kunt u geen nieuwe In-Place in Exchange Online. Maar u kunt de duur van de wachttijd van een In-Place in een inactief postvak wijzigen. Vanaf 1 oktober 2020 kunt u de duur van de wachttijd echter niet wijzigen. U kunt alleen een inactief postvak verwijderen door de In-Place verwijderen. Bestaande inactieve postvakken die in de wacht In-Place blijven behouden totdat de wacht wordt verwijderd. Zie Retirement of legacy eDiscovery tools (Oude eDiscovery-hulpprogramma's) voor meer informatie over het In-Place van [eDiscovery-functies.](legacy-ediscovery-retirement.md)
  
Zie de [sectie Meer informatie](#more-information) voor een beschrijving van wat er gebeurt nadat een postvak is verwijderd uit een inactief postvak.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Voordat u een inactief postvak verwijdert

- U moet powershell Exchange Online gebruiken om een geschil in een inactief postvak te verwijderen. U kunt het beheercentrum Exchange (EAC) niet gebruiken. Zie voor stapsgewijs instructies de [Verbinding maken powershell Exchange Online gebruiken.](/powershell/exchange/connect-to-exchange-online-powershell)

- U kunt de inhoud van een inactief postvak naar een ander postvak kopiëren voordat u de wacht houdt en een inactief postvak verwijdert. Zie Een [inactief postvak terugzetten in](restore-an-inactive-mailbox.md)Office 365 voor meer Office 365.

- Als u het bewaar- of bewaringsbeleid uit een inactief postvak verwijdert en de bewaarperiode voor het postvak is verlopen, wordt het postvak definitief verwijderd. Nadat het is verwijderd, kan het niet meer worden hersteld. Voordat u de wacht houdt, moet u ervoor zorgen dat u de inhoud in het postvak niet meer nodig hebt. Als u een inactief postvak opnieuw wilt activeren, kunt u het herstellen. Zie Een [inactief postvak herstellen in](recover-an-inactive-mailbox.md)Office 365 voor meer Office 365.

- Zie Inactieve postvakken in Office 365 voor meer informatie over inactieve [postvakken.](inactive-mailboxes-in-office-365.md)

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Stap 1: De inboxen in een inactief postvak identificeren

Zoals eerder vermeld, kan een beleid voor In-Place bewaring, bewaring of bewaring in een inactief postvak worden geplaatst. De eerste stap is het identificeren van de ophoudt in een inactief postvak.
  
Voer de volgende opdracht uit om de wachtgegevens weer te geven voor alle inactieve postvakken in uw organisatie.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

De waarde van **Waar** voor de **eigenschap LitigationHoldEnabled** geeft aan dat het inactieve postvak zich in de procesvaste procedure houdt. Als een In-Place in een inactief postvak wordt geplaatst, wordt de GUID voor de hold weergegeven als de waarde voor de eigenschap **InPlaceHolds.** Uit de volgende resultaten voor twee inactieve postvakken blijkt bijvoorbeeld dat er een procedurele bewaring wordt geplaatst op Ann Beebe en dat er een In-Place Bewaringsbeleid wordt geplaatst op Pilar Pinilla.
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Als een groot aantal In-Place bewaarbeleid in een inactief postvak wordt geplaatst, worden niet alle In-Place Guids voor bewaring weergegeven. U kunt de volgende opdracht uitvoeren om alle GUID's weer te geven in de eigenschap InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
Zie Het type wacht in een postvak identificeren voor meer informatie over het identificeren van [wachtvakken.](identify-a-hold-on-an-exchange-online-mailbox.md)

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Stap 2: Een greep uit een inactief postvak verwijderen

Nadat u hebt bepaald welk type wacht in het inactieve postvak wordt geplaatst (en of er meerdere wachtvakken zijn), is de volgende stap het verwijderen van de wacht in het postvak. Zoals eerder vermeld, moet u alle in- en uitvakken verwijderen om een inactief postvak definitief te verwijderen.
  
### <a name="remove-a-litigation-hold"></a>Een geschil in de wacht zetten verwijderen

Zoals eerder is aangegeven, moet u een Windows PowerShell om een geschil in een inactief postvak te verwijderen. U kunt het EAC niet gebruiken. Voer de volgende opdracht uit om een proces in de wacht te zetten.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> De beste manier om een inactief postvak te identificeren, is door de distinguished name of Exchange GUID-waarde te gebruiken. Als u een van deze waarden gebruikt, voorkomt u dat per ongeluk het verkeerde postvak wordt opgegeven. 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a>Een inactief postvak verwijderen uit een bewaarbeleid

De procedure voor het verwijderen van een inactief postvak uit een Microsoft 365 bewaarbeleid is afhankelijk van of het bewaarbeleid dat aan het inactieve postvak is toegewezen, organisatiebreed of expliciet is. over het type bewaarbeleid dat is toegewezen aan het inactieve postvak.

- Bewaarbeleid voor de hele organisatie dat is toegewezen aan alle postvakken in de organisatie. Gebruik de **Get-OrganizationConfig-cmdlet** in Exchange Online PowerShell voor informatie over bewaarbeleid voor de hele organisatie.

- Specifiek beleid voor het bewaren van locaties dat is toegewezen aan specifieke postvakken. Dit zijn beleidsregels die zijn toegewezen aan de inhoudslocaties van specifieke gebruikers. Gebruik de **cmdlet Get-Mailbox -IncludeInactiveMailbox** in Exchange Online PowerShell voor informatie over bewaarbeleid dat is toegewezen aan specifieke inactieve postvakken.

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a>Een inactief postvak verwijderen uit een bewaarbeleid voor de hele organisatie

Voer de volgende opdracht uit in Exchange Online PowerShell om een inactief postvak uit te sluiten van een bewaarbeleid voor de hele organisatie.

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

Zie de sectie 'Get-OrganizationConfig' in How to identify the type of hold placed on a mailbox (Get-OrganizationConfig) in How to identify the type of hold placed on a mailbox (Get-OrganizationConfig) (Get-OrganizationConfig) in How to identify the type of hold placed [on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)(Get-OrganizationConfig) (Get-OrganizationConfig) voor meer informatie over het bepalen van het bewaarbeleid voor een inactief postvak en het verkrijgen van de GUID voor een bewaarbeleid.

U kunt ook de volgende opdracht uitvoeren om het inactieve postvak te verwijderen uit alle beleidsregels voor de hele organisatie:

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a>Een inactief postvak verwijderen uit een specifiek bewaarbeleid voor locaties

Voer de volgende opdracht uit in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) om een inactief postvak te verwijderen uit een expliciet bewaarbeleid.

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

Zie de sectie Postvak IN in Het [type](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)bewaring dat in een postvak is geplaatst voor meer informatie over het specifieke beleid voor het bewaren van locaties dat is toegepast op een inactief postvak en het verkrijgen van de GUID voor een bewaarbeleid.

### <a name="remove-in-place-holds"></a>Houd In-Place verwijderen

 Er zijn twee manieren om een In-Place uit een inactief postvak te verwijderen: 
  
- **Verwijder het In-Place Hold-object**. Als het inactieve postvak dat u permanent wilt verwijderen, het enige bronpostvak is voor een In-Place-wacht, kunt u het In-Place Object in wacht houden. 

    > [!NOTE]
    > U moet de wacht houden uitschakelen voordat u een object In-Place verwijderen. Als u probeert een object In-Place hold te verwijderen waarin de wacht is ingeschakeld, ontvangt u een foutbericht. 
  
- **Verwijder het inactieve postvak als bronpostvak van een In-Place Wacht.** Als u andere bronpostvakken wilt behouden voor een In-Place Hold, kunt u het inactieve postvak verwijderen uit de lijst met bronpostvakken en het object In-Place behouden.

#### <a name="delete-an-in-place-hold"></a>Een wacht In-Place verwijderen

1. Maak een variabele met de eigenschappen van de In-Place Hold die u wilt verwijderen. Gebruik de In-Place GUID in de wacht houden die u hebt verkregen in stap 1: Identificeer de wacht in [een inactief postvak.](#step-1-identify-the-holds-on-an-inactive-mailbox)

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. De wacht op de In-Place uitschakelen.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Verwijder de In-Place Hold.

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a>Een inactief postvak uit een In-Place verwijderen

Als de In-Place een groot aantal bronpostvakken bevat, is het mogelijk dat het inactieve postvak niet wordt weergegeven op de pagina Bronnen in het EAC.  Er worden maximaal 3000 postvakken weergegeven  op de pagina Bronnen wanneer u een In-Place bewerken. Als een inactief postvak niet wordt  weergegeven op de pagina Bronnen, kunt u Exchange Online PowerShell gebruiken om het uit de In-Place verwijderen. 
  
1. Maak een variabele met de eigenschappen van de In-Place in het inactieve postvak. Gebruik de In-Place GUID in de wacht houden die u hebt verkregen in stap 1: Identificeer de wacht in [een inactief postvak.](#step-1-identify-the-holds-on-an-inactive-mailbox)

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Controleer of het inactieve postvak wordt weergegeven als een bronpostvak voor de In-Place Inactief. 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > De *eigenschap* Bronnen van de In-Place Hold identificeert de bronpostvakken aan de hand van de *eigenschappen van LegacyExchangeDN.* Omdat met deze eigenschap unieke inactieve postvakken worden geïdentificeerd, voorkomt u het verwijderen van het verkeerde postvak met de eigenschap Bronnen uit de In-Place Hold.  Dit helpt ook om problemen te voorkomen als twee postvakken dezelfde alias of SMTP-adres hebben. 

3. Verwijder het inactieve postvak uit de lijst met bronpostvakken in de variabele. Gebruik de **LegacyExchangeDN** van het inactieve postvak dat wordt geretourneerd door de opdracht in de vorige stap. 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    Met de volgende opdracht wordt bijvoorbeeld het inactieve postvak voor Pilar Pinilla verwijderd.

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. Controleer of het inactieve postvak is verwijderd uit de lijst met bronpostvakken in de variabele.

   ```powershell
   $InPlaceHold.Sources
   ```

5. Wijzig de In-Place De wacht houden met de bijgewerkte lijst met bronpostvakken, die niet het inactieve postvak bevat.

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Controleer of het inactieve postvak is verwijderd uit de lijst met bronpostvakken voor de In-Place in de wacht.

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Meer informatie

- **Een inactief postvak is een type postvak dat wordt verwijderd.** In Exchange Online is een zacht verwijderd postvak een postvak dat is verwijderd, maar binnen een specifieke bewaarperiode kan worden hersteld. Een eerder inactief postvak is 183 dagen beschikbaar als een zacht verwijderd postvak in Exchange Online 183 dagen. Dit betekent dat het postvak binnen 183 dagen na de soft-deleted kan worden hersteld. Na 183 dagen wordt een zacht verwijderd postvak gemarkeerd voor permanent verwijderen en kan het niet worden hersteld.

- **Wat gebeurt er nadat u de wacht op een inactief postvak hebt verwijderd?** Het postvak wordt behandeld als andere zacht verwijderde postvakken en is gemarkeerd voor permanente verwijdering nadat de bewaarperiode van het 183 dagen verwijderde postvak is verlopen. Deze bewaarperiode begint op de datum waarop het postvak voor het eerst inactief is gemaakt. Deze datum wordt de zacht verwijderde datum genoemd, de datum waarop het bijbehorende gebruikersaccount is verwijderd of wanneer het **Exchange Online-postvak** is verwijderd met de cmdlet Postvak verwijderen. De zacht verwijderde datum is niet de datum waarop u de wacht houdt.

- **Wordt een inactief postvak permanent verwijderd direct nadat de wacht is verwijderd?** Een voorheen inactief postvak is 183 dagen beschikbaar in de status van de soft-verwijderde postvak. Na 183 dagen wordt het postvak gemarkeerd voor permanente verwijdering.

- **Hoe geeft u informatie weer over een inactief postvak nadat de wacht is verwijderd?** Nadat een greep is verwijderd en het inactieve postvak weer wordt teruggevormd naar een zacht verwijderd postvak, wordt  het niet geretourneerd met de parameter *InactiveMailboxOnly* met de cmdlet Postvak IN. U kunt echter wel informatie over het postvak weergeven met de opdracht **Postvak -SoftDeletedMailbox.** Bijvoorbeeld:

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  In het bovenstaande voorbeeld geeft de *eigenschap WhenSoftDeleted* de datum aan die in dit voorbeeld 16 juni 2020 is. De *eigenschap WasInactiveMailbox* wordt weergegeven als omdat het eerder een `True` inactief postvak was. Het postvak wordt 183 dagen na 30 september 2020 definitief verwijderd.

