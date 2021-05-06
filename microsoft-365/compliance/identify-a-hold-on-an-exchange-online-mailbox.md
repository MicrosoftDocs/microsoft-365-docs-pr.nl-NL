---
title: Het type wacht in een postvak Exchange Online identificeren
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.custom:
- seo-marvel-apr2020
description: Lees hoe u de verschillende typen wacht in een postvak in een Exchange Online in een Microsoft 365.
ms.openlocfilehash: 0fdfbd4503a4ddffd2ce2dd97c6af42684aea293
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161902"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Het type wacht in een postvak Exchange Online identificeren

In dit artikel wordt uitgelegd hoe u in postvakken in Exchange Online postvakken in Microsoft 365.

Microsoft 365 biedt verschillende manieren waarop uw organisatie kan voorkomen dat postvakinhoud permanent wordt verwijderd. Hierdoor kan uw organisatie inhoud behouden om te voldoen aan nalevingsvoorschriften of tijdens juridische en andere soorten onderzoeken. Hier vindt u een lijst met de bewaarfuncties (ook wel *bewaarfuncties* genoemd) in Office 365:

- **[Procesrecht in de wacht](create-a-litigation-hold.md)zetten:** Houdt die zijn toegepast op postvakken van gebruikers in Exchange Online.

- **[eDiscovery-hold:](create-ediscovery-holds.md)** Houdt die zijn gekoppeld aan een Core eDiscovery-zaak in het beveiligings- en compliancecentrum. eDiscovery-holds kunnen worden toegepast op postvakken van gebruikers en op het bijbehorende postvak voor Microsoft 365 Groepen en Microsoft Teams.

- **[In-Place Hold](/Exchange/security-and-compliance/create-or-remove-in-place-holds):** Houdt die worden toegepast op postvakken van gebruikers met behulp van In-Place eDiscovery & in het Exchange-beheercentrum in Exchange Online. 

   > [!NOTE]
   > In-Place Holds zijn verwijderd en u kunt geen In-Place maken of toepassen op postvakken. De In-Place kan echter nog steeds worden toegepast op postvakken in uw organisatie. Daarom worden deze in dit artikel opgenomen. Zie Retirement [of legacy eDiscovery tools (Oude eDiscovery-hulpprogramma's) voor](legacy-ediscovery-retirement.md#in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center)meer informatie.

- **[Microsoft 365 bewaarbeleid:](retention.md)** Kan worden geconfigureerd om inhoud te behouden (of te behouden en vervolgens te verwijderen) in gebruikerspostvakken in Exchange Online en in het bijbehorende postvak voor Microsoft 365 Groepen en Microsoft Teams. U kunt ook een bewaarbeleid maken om gesprekken Skype voor Bedrijven behouden, die zijn opgeslagen in postvakken van gebruikers.

  Er zijn twee typen bewaarbeleid Microsoft 365 die aan postvakken kunnen worden toegewezen.

    - **Specifiek beleid voor het bewaren van locaties:** Dit zijn beleidsregels die zijn toegewezen aan de inhoudslocaties van specifieke gebruikers. U gebruikt de **cmdlet Postvak** in Exchange Online PowerShell om informatie te krijgen over bewaarbeleid dat aan specifieke postvakken is toegewezen. Zie de sectie A policy with specific inclusions or exclusions from the retention policy documentation (A policy with [specific inclusions](create-retention-policies.md#a-policy-with-specific-inclusions-or-exclusions) or exclusions from the retention policy documentation) voor meer informatie over dit type bewaarbeleid.

    - **Bewaarbeleid voor de hele organisatie:** Dit zijn beleidsregels die zijn toegewezen aan alle inhoudslocaties in uw organisatie. U gebruikt de **cmdlet Get-OrganizationConfig** in Exchange Online PowerShell om informatie te krijgen over bewaarbeleid voor de hele organisatie. Zie de sectie A-beleid dat van toepassing [is](create-retention-policies.md#a-policy-that-applies-to-entire-locations) op hele locaties uit de documentatie voor bewaarbeleid voor meer informatie over dit type bewaarbeleid.

- **[Microsoft 365](retention.md)bewaarlabels:** Als een gebruiker een bewaarlabel voor Microsoft 365 (een bewaarlabel dat is geconfigureerd om  inhoud te behouden of inhoud te behouden en vervolgens te verwijderen) op een map of item in zijn postvak gebruikt, wordt er een bewaring in het postvak geplaatst alsof het postvak is geplaatst in de bewaring van rechtszaken of is toegewezen aan een Microsoft 365-bewaarbeleid. Zie Postvakken identificeren in bewaring voor meer informatie omdat er een [bewaarlabel is](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item) toegepast op een map of itemsectie in dit artikel.

Als u postvakken in bewaring wilt beheren, moet u mogelijk bepalen welk type bewaring in een postvak is geplaatst, zodat u taken kunt uitvoeren, zoals het wijzigen van de duur van de bewaring, het tijdelijk of permanent verwijderen van de bewaring of het uitsluiten van een postvak uit een Microsoft 365 bewaarbeleid. In deze gevallen is de eerste stap het identificeren van het type wacht in het postvak. En omdat meerdere wachtvakken (en verschillende typen postvakken) in één postvak kunnen worden geplaatst, moet u alle in een postvak geplaatste in- of uitsleenvakken identificeren als u een wachtpost wilt verwijderen of wijzigen.

## <a name="step-1-obtain-the-guid-for-holds-placed-on-a-mailbox"></a>Stap 1: De GUID verkrijgen voor in een postvak geplaatste postvakken

U kunt de volgende twee cmdlets uitvoeren in Exchange Online PowerShell om de GUID te krijgen van de holdss die in een postvak zijn geplaatst. Nadat u een GUID hebt ontvangen, gebruikt u deze om de specifieke wacht in stap 2 te identificeren. Een procedure voor het in de wacht houden van rechtszaken wordt niet geïdentificeerd door een GUID. Het in- of uitschakelen van een postvak is ingeschakeld of uitgeschakeld.

- **Postvak in get:** Gebruik deze cmdlet om te bepalen In-Place Bewaring van rechtszaken is ingeschakeld voor een postvak en om de GUID's voor eDiscovery-bewaring, In-Place Bewaring en Microsoft 365 bewaarbeleid te krijgen die specifiek aan een postvak zijn toegewezen. De uitvoer van deze cmdlet geeft ook aan of een postvak expliciet is uitgesloten van een bewaarbeleid voor de hele organisatie.

- **Get-OrganizationConfig:** Gebruik deze cmdlet om de GUID's te krijgen voor bewaarbeleid voor de hele organisatie.

Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

### <a name="get-mailbox"></a>Get-Mailbox

Voer de volgende opdracht uit om informatie te krijgen over het bewaar- en Microsoft 365 bewaarbeleid dat is toegepast op een postvak.

```powershell
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> Als de eigenschap InPlaceHolds te veel waarden heeft en niet alle waarden worden weergegeven, kunt u de opdracht uitvoeren om elke GUID op een afzonderlijke regel `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` weer te geven.

In de volgende tabel wordt beschreven hoe u verschillende typen inhoudplaatsen kunt identificeren op basis van de waarden in de eigenschap *InPlaceHolds* wanneer u de cmdlet **Get-Mailbox** uitwerkt.

|Type wacht houden  |Voorbeeldwaarde  |De wacht houden identificeren  |
|---------|---------|---------|
|Proces in de wacht zetten     |    `True`     |     Litigation Hold is ingeschakeld voor een postvak wanneer de *eigenschap LitigationHoldEnabled* is ingesteld op `True` .    |
|eDiscovery-wacht     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   De *eigenschap InPlaceHolds* bevat de GUID van een hold die is gekoppeld aan een eDiscovery-zaak in het beveiligings- en compliancecentrum. U kunt zien dat dit een eDiscovery-hold is, omdat de GUID begint met het voorvoegsel (dat een `UniH` Unified Hold betekent).      |
|In-Place Hold     |     `c0ba3ce811b6432a8751430937152491` <br/> of <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     De *eigenschap InPlaceHolds* bevat de GUID van de In-Place Hold die in het postvak is geplaatst. U kunt zien dat dit een In-Place Omdat de GUID niet begint met een voorvoegsel of het begint met het `cld` voorvoegsel.     |
|Microsoft 365 bewaarbeleid dat specifiek is toegepast op het postvak     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> of <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     De eigenschap InPlaceHolds bevat GUID's van een specifiek beleid voor het bewaren van locaties dat is toegepast op het postvak. U kunt bewaarbeleid identificeren omdat de GUID begint met het `mbx` voorvoegsel of `skp` het voorvoegsel. Het voorvoegsel geeft aan dat het bewaarbeleid wordt toegepast op `skp` Skype voor Bedrijven gesprekken in het postvak van de gebruiker.    |
|Uitgesloten van een organisatiebrede Microsoft 365 bewaarbeleid     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     Als een postvak is uitgesloten van een organisatiebreed Microsoft 365 bewaarbeleid, wordt de GUID voor het bewaarbeleid waar het postvak van is uitgesloten, weergegeven in de eigenschap InPlaceHolds en wordt deze geïdentificeerd door het `-mbx` voorvoegsel.    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
Als de *eigenschap InPlaceHolds* leeg is wanneer u de **cmdlet** Postvak IN uitwerkt, is er mogelijk nog steeds een of meer beleidsregels voor Microsoft 365 voor het postvak toegepast. Voer de volgende opdracht uit in Exchange Online PowerShell om een lijst te krijgen met GUID's voor het Microsoft 365 bewaarbeleid.

```powershell
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> Als de eigenschap InPlaceHolds te veel waarden heeft en niet alle waarden worden weergegeven, kunt u de opdracht uitvoeren om elke GUID op een afzonderlijke regel `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` weer te geven.

In de volgende tabel worden de verschillende typen in de hele organisatie opgeslagen gegevens beschreven en wordt beschreven hoe u elk type kunt identificeren op basis van de GUID's in de eigenschap *InPlaceHolds* wanneer u de **cmdlet Get-OrganizationConfig** uitwerkt.

|Type wacht houden  |Voorbeeldwaarde  |Beschrijving  |
|---------|---------|---------|
|Microsoft 365 bewaarbeleid toegepast op Exchange postvakken, Exchange openbare mappen en Teams chats    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Bewaarbeleid voor de hele organisatie dat is toegepast op Exchange-postvakken, Exchange openbare mappen en 1xN-chats in Microsoft Teams worden geïdentificeerd door GUID's die beginnen met het `mbx` voorvoegsel. Opmerking 1xN-chats worden opgeslagen in het postvak van de afzonderlijke chatdeelnemers.      |
|Microsoft 365 bewaarbeleid toegepast op Microsoft 365 groepen en Teams kanaalberichten     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Bewaarbeleid voor de hele organisatie dat is toegepast op Microsoft 365 groepen en kanaalberichten in Microsoft Teams worden geïdentificeerd door GUID's die beginnen met het `grp` voorvoegsel. Berichten met een notitiekanaal worden opgeslagen in het groepspostvak dat is gekoppeld aan een Microsoft-team.     |

Zie Meer informatie over bewaarbeleid voor Microsoft Teams bewaarbeleid voor [Microsoft Teams.](retention-policies-teams.md)

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>Inzicht in de opmaak van de InPlaceHolds-waarde voor bewaarbeleid

Naast het voorvoegsel (mbx, skp of grp) dat een item in de eigenschap InPlaceHolds identificeert als een Microsoft 365-bewaarbeleid, bevat de waarde ook een achtervoegsel dat het type bewaaractie aangeeft dat is geconfigureerd voor het beleid. Het actieachtervoegsel is bijvoorbeeld vet gemarkeerd in de volgende voorbeelden:

   `skp127d7cf1076947929bf136b7a2a8c36f`**:1**

   `mbx7cfb30345d454ac0a989ab3041051209`**:2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**:3**

De volgende tabel definieert de drie mogelijke bewaaracties:

|Waarde  |Beschrijving  |
|---------|---------|
|**1**     | Hiermee wordt aangegeven dat het bewaarbeleid is geconfigureerd om items te verwijderen. In het beleid worden geen items bewaard.        |
|**2**    |    Hiermee wordt aangegeven dat het bewaarbeleid is geconfigureerd voor het bewaren van items. Het beleid verwijdert geen items nadat de bewaarperiode is verlopen.     |
|**3**     |   Geeft aan dat het bewaarbeleid is geconfigureerd om items vast te houden en vervolgens te verwijderen nadat de bewaarperiode is verlopen.      |

Zie de sectie Inhoud behouden voor een bepaalde periode voor meer informatie over [bewaaracties.](create-retention-policies.md#retaining-content-for-a-specific-period-of-time)
   
## <a name="step-2-use-the-guid-to-identify-the-hold"></a>Stap 2: De GUID gebruiken om de wacht te identificeren

Nadat u de GUID hebt ontvangen voor een hold die is toegepast op een postvak, is de volgende stap het gebruik van deze GUID om de wacht te identificeren. In de volgende secties wordt be informatie gegeven over het identificeren van de naam van de wacht (en andere informatie) met behulp van de hold-GUID.

### <a name="ediscovery-holds"></a>eDiscovery-bezit

Voer de volgende opdrachten uit in & Compliance center PowerShell om een eDiscovery-hold te identificeren die is toegepast op het postvak. Gebruik de GUID (niet inclusief het UniH-voorvoegsel) voor de eDiscovery-hold die u hebt geïdentificeerd in stap 1. 

Zie Verbinding maken Security & Compliance Center PowerShell als u verbinding wilt maken met & [Compliance Center PowerShell.](/powershell/exchange/connect-to-scc-powershell)

Met de eerste opdracht wordt een variabele gemaakt die informatie over de wacht houdt. Deze variabele wordt gebruikt in de andere opdrachten. In de tweede opdracht wordt de naam weergegeven van de eDiscovery-zaak waar de wacht aan is gekoppeld. De derde opdracht geeft de naam van de wacht en een lijst weer met de postvakken waar de wacht op van toepassing is.

```powershell
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```powershell
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```powershell
$CaseHold | FL Name,ExchangeLocation
```

### <a name="in-place-holds"></a>In-Place Holds

Voer de volgende opdracht uit in Exchange Online PowerShell om de In-Place te identificeren die is toegepast op het postvak. Gebruik de GUID voor de In-Place Hold die u hebt geïdentificeerd in stap 1. De opdracht bevat de naam van de wacht en een lijst met de postvakken waar de wacht op van toepassing is.

```powershell
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```

Als de GUID voor de In-Place met het voorvoegsel begint, moet u het voorvoegsel opnemen bij het uitvoeren `cld` van de vorige opdracht.

> [!IMPORTANT]
> Terwijl we op verschillende manieren blijven investeren om postvakinhoud te behouden, kondigen we de uittreding aan van In-Place Holds in het Exchange admin center (EAC). Vanaf 1 juli 2020 kunt u geen nieuwe In-Place in Exchange Online. Maar u kunt nog steeds de In-Place in de EAC  beheren of met de cmdlet Postvak Zoeken instellen in Exchange Online PowerShell. Vanaf 1 oktober 2020 kunt u de In-Place beheren. U verwijdert ze alleen in het EAC of met de cmdlet **Remove-MailboxSearch.** Zie Retirement of legacy eDiscovery tools (Oude eDiscovery-hulpprogramma's) voor meer informatie over het In-Place van [eDiscovery-functies.](legacy-ediscovery-retirement.md)

### <a name="microsoft-365-retention-policies"></a>Microsoft 365 bewaarbeleid

Voer de volgende opdracht uit in Security & Compliance Center PowerShell om de identiteit te bepalen van het Microsoft 365 bewaarbeleid (organisatiebrede of specifieke locatie) dat is toegepast op het postvak. Gebruik de GUID (niet inclusief het mbx-, skp- of grp-voorvoegsel of het actieachtervoegsel) dat u hebt geïdentificeerd in stap 1.

```powershell
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>Postvakken in bewaring identificeren omdat er een bewaarlabel is toegepast op een map of item

Wanneer een gebruiker een bewaarlabel gebruikt dat is geconfigureerd om inhoud te behouden of te behouden en vervolgens inhoud te verwijderen naar een map of item in het postvak, is de eigenschap *ComplianceTagHoldApplied-postvak* ingesteld op **Waar.** Wanneer dit gebeurt, wordt het postvak beschouwd als in bewaring, alsof het is geplaatst in de bewaring van rechtszaken of is toegewezen aan een Microsoft 365 bewaarbeleid. Wanneer de *eigenschap ComplianceTagHoldApplied* is ingesteld op **Waar,** kunnen de volgende dingen optreden:

- Als het postvak of het gebruikersaccount van de gebruiker wordt verwijderd, wordt het postvak een [inactief postvak.](inactive-mailboxes-in-office-365.md)
- U kunt het postvak niet uitschakelen (het primaire postvak of het archiefpostvak als dit is ingeschakeld).
- Items in het postvak blijven mogelijk langer behouden dan verwacht. Dit komt omdat het postvak in de wacht staat en er daarom geen items permanent worden verwijderd (verwijderd).

Als u de waarde van de eigenschap *ComplianceTagHoldApplied* wilt weergeven, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell:

```powershell
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

Zie bewaarlabels voor meer [informatie over bewaarlabels.](retention.md#retention-labels)

## <a name="managing-mailboxes-on-delay-hold"></a>Postvakken beheren bij vertragingsvertraging

Nadat een type wachtstand uit een postvak is verwijderd, wordt *een vertragingsvertraging* toegepast. Dit betekent dat de feitelijke verwijdering van de wacht wordt uitgesteld tot 30 dagen om te voorkomen dat gegevens permanent worden verwijderd (verwijderd) uit het postvak. Dit biedt beheerders de mogelijkheid om postvakitems te zoeken of te herstellen die worden verwijderd nadat een greep is verwijderd. Een vertragingsvertraging wordt op een postvak geplaatst wanneer de volgende keer dat de assistent voor beheerde mappen het postvak verwerkt en detecteert dat een wachtstand is verwijderd. In het bijzonder wordt een vertragingsvertraging toegepast op een postvak wanneer de assistent voor beheerde mappen een van de volgende postvakeigenschappen in stelt op **Waar:**

- **DelayHoldApplied:** Deze eigenschap is van toepassing op e-mailgerelateerde inhoud (die wordt gegenereerd door personen die gebruikmaken van Outlook en Outlook op het web) die is opgeslagen in het postvak van een gebruiker.

- **DelayReleaseHoldApplied:** Deze eigenschap is van toepassing op cloudinhoud (gegenereerd door niet-Outlook-apps zoals Microsoft Teams, Microsoft Forms en Microsoft Yammer) die is opgeslagen in het postvak van een gebruiker. Cloudgegevens die door een Microsoft-app worden gegenereerd, worden meestal opgeslagen in een verborgen map in het postvak van een gebruiker.

Wanneer een vertragingsbehoud in het postvak wordt geplaatst (wanneer een van de vorige eigenschappen is ingesteld op **Waar),** wordt het postvak nog steeds beschouwd als in de wachtstand voor een onbeperkte duur van de wachtstand, alsof het postvak in de wachtstand staat. Na 30 dagen verloopt de vertragingstermijn en Microsoft 365 probeert automatisch de vertragingsbehoud te verwijderen (door de eigenschap DelayHoldApplied of DelayReleaseHoldApplied in te stellen op **Onwaar)** zodat de wachtstand wordt verwijderd. Nadat een van deze eigenschappen is ingesteld op Onwaar, worden de bijbehorende items die zijn gemarkeerd voor verwijdering, verwijderd wanneer het postvak de volgende keer wordt verwerkt door de Assistent voor beheerde mappen.

Als u de waarden voor de eigenschappen DelayHoldApplied en DelayReleaseHoldApplied voor een postvak wilt weergeven, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell.

```powershell
Get-Mailbox <username> | FL *HoldApplied*
```

Als u de vertragingstermijn wilt verwijderen voordat deze verloopt, kunt u een (of beide) de volgende opdrachten uitvoeren in Exchange Online PowerShell, afhankelijk van de eigenschap die u wilt wijzigen:

```powershell
Set-Mailbox <username> -RemoveDelayHoldApplied
```

Of

```powershell
Set-Mailbox <username> -RemoveDelayReleaseHoldApplied
```

U moet de rol Legal Hold in Exchange Online toegewezen krijgen om de parameters *RemoveDelayHoldApplied* of *RemoveDelayReleaseHoldApplied te* gebruiken. 

Als u de vertragingsophoud voor een inactief postvak wilt verwijderen, voert u een van de volgende opdrachten uit in Exchange Online PowerShell:

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

Of

```powershell
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayReleaseHoldApplied
```

> [!TIP]
> De beste manier om een inactief postvak in de vorige opdracht op te geven, is door de distinguished name of Exchange GUID-waarde te gebruiken. Als u een van deze waarden gebruikt, voorkomt u dat per ongeluk het verkeerde postvak wordt opgegeven. 

Zie [Postvak instellen](/powershell/module/exchange/set-mailbox)voor meer informatie over het gebruik van deze parameters voor het beheren van vertragingsbeheer.

Houd rekening met de volgende zaken bij het beheren van een postvak in de wachtstand:

- Als de eigenschap DelayHoldApplied of DelayReleaseHoldApplied is ingesteld op **Waar** en een postvak (of het bijbehorende gebruikersaccount) wordt verwijderd, wordt het postvak een inactief postvak. Dat komt omdat een postvak wordt beschouwd als in de wacht als een van de eigenschappen is ingesteld op Waar **en** als u een postvak in de wacht houdt, resulteert dit in een inactief postvak. Als u een postvak wilt verwijderen en er geen inactief postvak van wilt maken, moet u beide eigenschappen instellen op **Onwaar.**

- Zoals eerder vermeld, wordt een postvak beschouwd als in de wachtstand voor een onbeperkte duur als de eigenschap DelayHoldApplied of DelayReleaseHoldApplied is ingesteld op **True**. Dit betekent echter niet dat alle *inhoud* in het postvak behouden blijft. Dit hangt af van de waarde die is ingesteld op elke eigenschap. Stel dat beide eigenschappen zijn ingesteld op **Waar,** omdat de postvakken worden verwijderd uit het postvak. Vervolgens verwijdert u alleen de vertragingsopslag die is toegepast op niet-Outlook cloudgegevens (met de parameter *RemoveDelayReleaseHoldApplied).* De volgende keer dat de Assistent voor beheerde mappen het postvak verwerkt, worden de niet-Outlook items verwijderd die zijn gemarkeerd voor verwijdering. Alle Outlook items die zijn gemarkeerd voor verwijdering, worden niet verwijderd omdat de eigenschap DelayHoldApplied nog steeds is ingesteld op **Waar**. Het tegenovergestelde zou ook waar zijn: als  DelayHoldApplied is ingesteld op Onwaar en DelayReleaseHoldApplied is ingesteld op **Waar,** worden alleen Outlook items verwijderd die zijn gemarkeerd voor verwijdering.

## <a name="next-steps"></a>Volgende stappen

Nadat u de bewaringen hebt gevonden die zijn toegepast op een postvak, kunt u taken uitvoeren, zoals het wijzigen van de duur van de bewaring, het tijdelijk of definitief verwijderen van de bewaring of het uitsluiten van een inactief postvak uit een Microsoft 365 bewaarbeleid. Zie een van de volgende onderwerpen voor meer informatie over het uitvoeren van taken met betrekking tot in- en uit te voeren:

- Voer de opdracht [Set-RetentionCompliancePolicy -Identity \<Policy Name> -AddExchangeLocationException \<user mailbox> ](/powershell/module/exchange/set-retentioncompliancepolicy) uit in Security & Compliance Center PowerShell om een postvak uit te sluiten van een Microsoft 365 bewaarbeleid voor de hele organisatie. Deze opdracht kan alleen worden gebruikt voor bewaarbeleid waarbij de waarde voor de *eigenschap ExchangeLocation* gelijk is aan `All` .

- [De duur van bewaring van een inactief postvak wijzigen](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Een inactief postvak verwijderen](delete-an-inactive-mailbox.md)

- [Items verwijderen in de map Herstelbare items van postvakken in de cloud in de wacht](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)