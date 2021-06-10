---
title: Postvakcontrole beheren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
ms.custom: seo-marvel-apr2020
description: Logboekregistratie voor postvakkencontrole is standaard ingeschakeld in Microsoft 365 (standaard ook wel standaardpostvakcontrole of postvakcontrole genoemd). Dit betekent dat bepaalde acties die worden uitgevoerd door postvakeigenaren, gedelegeerden en beheerders, automatisch worden aangemeld in een postvakauditlogboek, waar u kunt zoeken naar activiteiten die in het postvak worden uitgevoerd.
ms.openlocfilehash: c77e96adfee40027beb653c9e725141fc8d7a8fe
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866641"
---
# <a name="manage-mailbox-auditing"></a>Postvakcontrole beheren

Vanaf januari 2019 wordt auditregistratie voor postvakken standaard ingeschakeld voor alle organisaties. Dit betekent dat bepaalde acties die door postvakeigenaren, gedelegeerden en beheerders worden uitgevoerd, automatisch worden vastgelegd en dat de bijbehorende auditrecords voor postvakken beschikbaar zijn wanneer u ze zoekt in het postvakauditlogboek. Voordat postvakcontrole standaard is ingeschakeld, moest u dit handmatig inschakelen voor elk gebruikerspostvak in uw organisatie.

Hier zijn enkele voordelen van postvakcontrole standaard ingeschakeld:

- Controle wordt automatisch ingeschakeld wanneer u een nieuw postvak maakt. U hoeft het niet handmatig in te stellen voor nieuwe gebruikers.
- U hoeft de postvakacties die worden gecontroleerd niet te beheren. Een vooraf gedefinieerde set postvakacties wordt standaard gecontroleerd voor elk aanmeldingstype (beheerder, gedelegeerde en eigenaar).
- Wanneer Microsoft een nieuwe postvakactie publiceert, wordt de actie mogelijk automatisch toegevoegd aan de lijst met postvakacties die standaard worden gecontroleerd (afhankelijk van de gebruiker met de juiste licentie). Dit betekent dat u het toevoegen van nieuwe acties in postvakken niet hoeft te controleren.
- U hebt een consistent beleid voor het controleren van postvakken in uw organisatie (omdat u dezelfde acties voor alle postvakken controleert).

> [!NOTE]
>
> - Het belangrijkste om te onthouden over de standaardversie van postvakcontrole is: u hoeft niets te doen om de postvakcontrole te beheren. Voor meer informatie, het aanpassen van postvakcontrole via de standaardinstellingen of het helemaal uitschakelen, kan dit artikel u helpen.
> - Standaard zijn alleen postvakauditgebeurtenissen voor E5-gebruikers beschikbaar in zoekopdrachten in het auditlogboek in het Beveiligings- & Compliancecentrum of via de Office 365 Management Activity API. Zie de sectie Meer [informatie](#more-information) in dit artikel voor meer informatie.

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>Controleren of postvakcontrole standaard is ingeschakeld

Als u wilt controleren of postvakcontrole standaard is ingeschakeld voor uw organisatie, moet u de volgende opdracht uitvoeren in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

```PowerShell
Get-OrganizationConfig | Format-List AuditDisabled
```

De waarde **Onwaar** geeft aan dat postvakcontrole standaard is ingeschakeld voor de organisatie. Deze standaardinstelling voor organisatiewaarde overteert de instelling voor het controleren van postvakken op specifieke postvakken. Als het controleren van postvakken bijvoorbeeld is uitgeschakeld voor een postvak (de eigenschap *AuditEnabled* is **Onwaar** in het postvak), worden de standaardpostvakacties nog steeds gecontroleerd voor het postvak, omdat postvakcontrole standaard is ingeschakeld voor de organisatie.

Als u het controleren van postvakken wilt uitgeschakeld voor specifieke postvakken, configureert u de bypass voor postvakcontrole voor de eigenaar van het postvak en andere gebruikers die toegang hebben tot het postvak. Zie de sectie Logboekregistratie voor [postvakken](#bypass-mailbox-audit-logging) omzeilen in dit artikel voor meer informatie.

> [!NOTE]
> Wanneer postvakcontrole standaard is ingeschakeld voor de organisatie, wordt de eigenschap *AuditEnabled* voor de betreffende postvakken niet gewijzigd van Onwaar **in** **Waar.** Met andere woorden: de eigenschap *AuditEnabled* in postvakken wordt standaard genegeerd door postvakken.

## <a name="supported-mailbox-types"></a>Ondersteunde postvaktypen

In de volgende tabel ziet u de postvaktypen die momenteel standaard worden ondersteund door postvakcontrole:

<br>

****

|Postvaktype|Ondersteund|
|---|:---:|
|Postvakken van gebruikers|![Vinkje](../media/checkmark.png)|
|Gedeelde postvakken|![Vinkje](../media/checkmark.png)|
|Microsoft 365 Postvakken groepeert|![Vinkje](../media/checkmark.png)|
|Resourcepostvakken||
|Postvakken in openbare mappen||
|

## <a name="logon-types-and-mailbox-actions"></a>Aanmeldingstypen en postvakacties

Aanmeldingstypen classificeren de gebruiker die de gecontroleerde acties in het postvak heeft uitgevoerd. In de volgende lijst worden de aanmeldingstypen beschreven die worden gebruikt in de logboekregistratie voor postvakken:

- **Eigenaar:** de eigenaar van het postvak (het account dat is gekoppeld aan het postvak).
- **Gedelegeerde**:
  - Een gebruiker aan wie de machtiging SendAs, SendOnBehalf of FullAccess is toegewezen aan een ander postvak.
  - Een beheerder aan wie de machtiging FullAccess is toegewezen aan het postvak van een gebruiker.
- **Beheerder**:
  - Het postvak wordt doorzocht met een van de volgende Microsoft eDiscovery-hulpprogramma's:
    - Zoeken naar inhoud in het compliancecentrum.
    - eDiscovery of Advanced eDiscovery in het Compliancecentrum.
    - In-Place eDiscovery in Exchange Online.
  - Het postvak wordt toegankelijk met behulp van Microsoft Exchange Server MAPI Editor.

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>Postvakacties voor gebruikerspostvakken en gedeelde postvakken

In de volgende tabel worden de postvakacties beschreven die beschikbaar zijn in de logboekregistratie voor postvakken van gebruikers en gedeelde postvakken.

- Een vinkje ( ![vinkje](../media/checkmark.png)) geeft aan dat de postvakactie kan worden geregistreerd voor het aanmeldingstype (niet alle acties zijn beschikbaar voor alle aanmeldingstypen).
- Een sterretje () nadat het vinkje aangeeft dat de postvakactie standaard is vastgelegd <sup>\*</sup> voor het aanmeldingstype.
- Een beheerder met volledige toegangsmachtiging voor een postvak wordt beschouwd als gemachtigde.

<br>

****

|Postvakactie|Omschrijving|Beheerder|Gemachtigde|Eigenaar|
|---|---|:---:|:---:|:---:|
|**AddFolderPermissions(AddFolderPermissions)**|Hoewel deze waarde wordt geaccepteerd als een postvakactie, is deze al opgenomen in de **actie UpdateFolderPermissions** en wordt deze niet afzonderlijk gecontroleerd. Met andere woorden, gebruik deze waarde niet.||||
|**Record toepassen**|Een item wordt als record gelabeld.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**Kopiëren**|Er is een bericht naar een andere map gekopieerd.|![Vinkje](../media/checkmark.png)|||
|**Maken**|Er is een item gemaakt in de map Agenda, Contactpersonen, Notities of Taken in het postvak (er wordt bijvoorbeeld een nieuw vergaderverzoek gemaakt). Het maken, verzenden of ontvangen van een bericht wordt niet gecontroleerd. Ook het maken van een postvak wordt niet gecontroleerd.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)|
|**MapBind**|Er is een postvakmap toegankelijk. Deze actie wordt ook vastgelegd wanneer de beheerder of gedelegeerde het postvak opent. <br/><br/> **Opmerking:** Auditrecords voor mapbindacties die door gedelegeerden worden uitgevoerd, worden samengevoegd. Eén auditrecord wordt gegenereerd voor afzonderlijke maptoegang binnen een periode van 24 uur.|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)||
|**HardDelete**|Er is een bericht verwijderd uit de map Herstelbare items.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**MailboxLogin**|De gebruiker heeft zich aangemeld bij zijn of haar postvak.|||![Vinkje](../media/checkmark.png)|
|**MailItemsAccessed**|**Opmerking:** Deze waarde is alleen beschikbaar voor gebruikers van E5- of E5-abonnementsabonnementen. Zie Geavanceerd controleren instellen [in Microsoft 365.](set-up-advanced-audit.md) <p> E-mailgegevens worden toegankelijk via e-mailprotocollen en -clients.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**MessageBind**|**Opmerking:** Deze waarde is alleen beschikbaar voor E3-gebruikers (gebruikers zonder E5- of E5 Compliance-invoegabonnementen). <p> Een bericht is bekeken in het voorbeeldvenster of geopend door een beheerder.|![Vinkje](../media/checkmark.png)|||
|**ModifyFolderPermissions**|Hoewel deze waarde wordt geaccepteerd als een postvakactie, is deze al opgenomen in de **actie UpdateFolderPermissions** en wordt deze niet afzonderlijk gecontroleerd. Met andere woorden, gebruik deze waarde niet.|||||
|**Move**|Een bericht is naar een andere map verplaatst.|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|
|**MoveToDeletedItems**|Een bericht is verwijderd en verplaatst naar de map Verwijderde items.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**RecordDelete**|Een item dat als record is gelabeld, is zacht verwijderd (verplaatst naar de map Herstelbare items). Items die als records zijn gelabeld, kunnen niet permanent worden verwijderd (verwijderd uit de map Herstelbare items).|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|
|**RemoveFolderPermissions**|Hoewel deze waarde wordt geaccepteerd als een postvakactie, is deze al opgenomen in de **actie UpdateFolderPermissions** en wordt deze niet afzonderlijk gecontroleerd. Met andere woorden, gebruik deze waarde niet.||||
|**SearchQueryInitiated**|**Opmerking:** Deze waarde is alleen beschikbaar voor gebruikers van E5- of E5-abonnementsabonnementen. Zie Geavanceerd controleren instellen [in Microsoft 365.](set-up-advanced-audit.md) <p> Een persoon gebruikt Outlook (Windows, Mac, iOS, Android of Outlook op het web) of de mail-app voor Windows 10 om te zoeken naar items in een postvak.|||![Vinkje](../media/checkmark.png)|
|**Send**|**Opmerking:** Deze waarde is alleen beschikbaar voor gebruikers van E5- of E5-abonnementsabonnementen. Zie Geavanceerd controleren instellen [in Microsoft 365.](set-up-advanced-audit.md) <p> De gebruiker verzendt een e-mailbericht, beantwoordt een e-mailbericht of stuurt een e-mailbericht door.|![Vinkje](../media/checkmark.png)<sup>\*</sup>||![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Een bericht is verzonden met de machtiging Verzenden als. Dit betekent dat een andere gebruiker het bericht heeft verzonden alsof het afkomstig is van de eigenaar van het postvak.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Een bericht is verzonden met de machtiging Verzenden namens. Dit betekent dat een andere gebruiker het bericht heeft verzonden namens de eigenaar van het postvak. Het bericht geeft aan de geadresseerde aan wie het bericht is verzonden namens en wie het bericht daadwerkelijk heeft verzonden.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Een bericht is definitief verwijderd of verwijderd uit de map Verwijderde items. Snel verwijderde items worden verplaatst naar de map Herstelbare items.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**Update**|Een bericht (of de eigenschappen ervan) is (zijn) gewijzigd.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|Er is een agendadelegatie toegewezen aan een postvak. Agendadelegering geeft iemand anders in dezelfde organisatie machtigingen voor het beheren van de agenda van de eigenaar van het postvak.|![Vinkje](../media/checkmark.png)<sup>\*</sup>||![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**UpdateComplianceTag**|Er wordt een ander bewaarlabel toegepast op een e-mailitem (aan een item kan slechts één bewaarlabel zijn toegewezen).|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|![Vinkje](../media/checkmark.png)|
|**UpdateFolderPermissions**|Een mapmachtiging is gewijzigd. Mapmachtigingen bepalen welke gebruikers in uw organisatie toegang hebben tot mappen in een mailbox en tot de berichten in die mappen.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**UpdateInboxRules**|Er is een regel voor postvak IN toegevoegd, verwijderd of gewijzigd. Regels voor Postvak IN worden gebruikt om berichten in het Postvak IN van de gebruiker te verwerken op basis van de opgegeven voorwaarden en acties uit te voeren wanneer aan de voorwaarden van een regel wordt voldaan, zoals het verplaatsen van een bericht naar een opgegeven map of het verwijderen van een bericht.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|

> [!IMPORTANT]
> Als u de postvakacties hebt aangepast  om te controleren op een aanmeldingstype voordat de postvakcontrole standaard is ingeschakeld in uw organisatie, blijven de aangepaste instellingen behouden in het postvak en worden ze niet overschreven door de standaardpostvakacties zoals beschreven in deze sectie. Als u de acties in het auditpostvak wilt herstellen naar [](#restore-the-default-mailbox-actions) de standaardwaarden (die u op elk moment kunt doen), gaat u naar de sectie Standaardpostvakacties herstellen verder in dit artikel.

### <a name="mailbox-actions-for-microsoft-365-group-mailboxes"></a>Postvakacties voor Microsoft 365 Groepspostvakken

Door postvakcontrole standaard in te stellen, wordt de logboekregistratie voor postvakken in postvakken van Microsoft 365 Groeperen weergegeven, maar u kunt niet aanpassen wat er wordt geregistreerd (u kunt postvakacties die zijn aangemeld voor elk aanmeldingstype niet toevoegen of verwijderen).

In de volgende tabel worden de postvakacties beschreven die standaard zijn vastgelegd op Microsoft 365 Postvakken groepeert voor elk aanmeldingstype.

Een beheerder met volledige toegangsmachtigingen voor een Microsoft 365 groepspostvak wordt beschouwd als gedelegeerde.

<br>

****

|Postvakactie|Omschrijving|Beheerder|Gemachtigde|Eigenaar|
|---|---|:---:|:---:|:---:|
|**Maken**|Een agenda-item maken. Het maken, verzenden of ontvangen van een bericht wordt niet gecontroleerd.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>||
|**HardDelete**|Er is een bericht verwijderd uit de map Herstelbare items.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**MoveToDeletedItems**|Een bericht is verwijderd en verplaatst naar de map Verwijderde items.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**SendAs**|Een bericht is verzonden met de machtiging Verzenden als.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>||
|**SendOnBehalf**|Een bericht is verzonden met de machtiging Verzenden namens.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>||
|**SoftDelete**|Een bericht is definitief verwijderd of verwijderd uit de map Verwijderde items. Snel verwijderde items worden verplaatst naar de map Herstelbare items.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|**Update**|Een bericht (of de eigenschappen ervan) is (zijn) gewijzigd.|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|![Vinkje](../media/checkmark.png)<sup>\*</sup>|
|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>Controleren of standaardpostvakacties worden geregistreerd voor elk aanmeldingstype

Standaardpostvakcontrole wordt een nieuwe *eigenschap DefaultAuditSet* toegevoegd aan alle postvakken. De waarde van deze eigenschap geeft aan of de standaardpostvakacties (beheerd door Microsoft) in het postvak worden gecontroleerd.

Als u de waarde wilt weergeven in gebruikerspostvakken of gedeelde postvakken, vervangt u de naam, alias, e-mailadres of gebruikersnaam (gebruikersnaam) van het postvak en voer u de volgende opdracht \<MailboxIdentity\> uit in Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Als u de waarde wilt weergeven Microsoft 365 groepspostvakken, vervangt u de naam, alias of het e-mailadres van het gedeelde postvak en voer u de volgende opdracht \<MailboxIdentity\> uit in Exchange Online PowerShell:

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

De waarde `Admin, Delegate, Owner` geeft aan:

- De standaardpostvakacties voor alle drie aanmeldingstypen worden gecontroleerd. Dit is de enige waarde die u ziet in Microsoft 365 Groepspostvakken.
- Een beheerder *heeft de gecontroleerde* postvakacties niet gewijzigd voor een aanmeldingstype in een gebruikerspostvak of een gedeeld postvak. Let op: dit is de standaardtoestand nadat postvakcontrole standaard is ingeschakeld in uw organisatie.

Als een beheerder ooit de postvakacties heeft gewijzigd die worden gecontroleerd op een aanmeldingstype (met behulp van de parameters *AuditAdmin,* *AuditDelegate* of *AuditOwner* op de cmdlet **Postvak** instellen), is de eigenschapswaarde anders.

De waarde voor de `Owner` eigenschap *DefaultAuditSet* in een gebruikerspostvak of gedeeld postvak geeft bijvoorbeeld aan:

- De standaardpostvakacties voor de eigenaar van het postvak worden gecontroleerd.
- De gecontroleerde postvakacties voor de `Delegate` typen en aanmeldingstypen zijn gewijzigd in de `Admin` standaardacties.

Een lege waarde voor de eigenschap *DefaultAuditSet* geeft aan dat de postvakacties voor alle drie aanmeldingstypen zijn gewijzigd in het gebruikerspostvak of een gedeeld postvak.

Zie de sectie Postvakacties wijzigen of herstellen [die](#change-or-restore-mailbox-actions-logged-by-default) standaard zijn vastgelegd in dit artikel voor meer informatie.

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>De postvakacties weergeven die worden aangemeld bij postvakken

Als u de postvakacties wilt zien die momenteel worden aangemeld bij gebruikerspostvakken of gedeelde postvakken, vervangt u door de naam, alias, e-mailadres of gebruikersnaam (gebruikersnaam) van het postvak en voert u een of meer van de volgende opdrachten \<MailboxIdentity\> uit in Exchange Online PowerShell.

> [!NOTE]
> Hoewel u de schakelknop kunt toevoegen aan de volgende opdrachten voor Postvak Microsoft 365 postvakken groepeert, kunt u de waarden die worden geretourneerd niet `-GroupMailbox` geloven.  De standaard- en statische postvakacties die worden gecontroleerd voor Microsoft 365 Groepspostvakken worden beschreven in de sectie Postvakacties voor [Microsoft 365 Groepspostvakken](#mailbox-actions-for-microsoft-365-group-mailboxes) eerder in dit artikel.

#### <a name="owner-actions"></a>Acties van eigenaar

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>Acties voor gedelegeerden

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>Beheeracties

```PowerShell
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>Standaard vastgelegde postvakacties wijzigen of herstellen

Zoals eerder is uitgelegd, is een van de belangrijkste voordelen van het standaard controleren van postvakken: u hoeft de gecontroleerde postvakkenacties niet te beheren. Microsoft doet dit voor u en we voegen automatisch nieuwe postvakacties toe die standaard moeten worden gecontroleerd wanneer ze worden uitgebracht.

Het is echter mogelijk dat uw organisatie een andere set postvakacties moet controleren voor postvakken van gebruikers en gedeelde postvakken. In de procedures in deze sectie ziet u hoe u de postvakacties wijzigt die voor elk aanmeldingstype worden gecontroleerd en hoe u terug kunt keren naar de door Microsoft beheerde standaardacties.

> [!IMPORTANT]
> Als u de volgende procedures gebruikt om de postvakacties aan te passen die zijn aangemeld bij gebruikerspostvakken of gedeelde postvakken, worden nieuwe standaardpostvakacties die door Microsoft zijn uitgebracht, niet automatisch gecontroleerd op die postvakken. U moet handmatig nieuwe postvakacties toevoegen aan uw aangepaste lijst met acties.

### <a name="change-the-mailbox-actions-to-audit"></a>De postvakacties wijzigen die u wilt controleren

U kunt de parameters *AuditAdmin,* *AuditDelegate* of *AuditOwner* op de **cmdlet** Postvak instellen gebruiken om de postvakacties te wijzigen die worden gecontroleerd voor gebruikerspostvakken en gedeelde postvakken (gecontroleerde acties voor Microsoft 365 groepspostvakken kunnen niet worden aangepast).

U kunt twee verschillende methoden gebruiken om de postvakacties op te geven:

- *Vervang* (overschrijf) de bestaande postvakacties met behulp van deze syntaxis: `action1,action2,...actionN` .
- *Postvakacties toevoegen* of verwijderen zonder dat dit van invloed is op andere bestaande waarden met behulp van deze `@{Add="action1","action2",..."actionN"}` syntaxis: of `@{Remove="action1","action2",..."actionN"}` .

In dit voorbeeld worden de acties voor het beheerderspostvak voor het postvak met de naam 'Gabriela Laureano' gewijzigd door de standaardacties met SoftDelete en HardDelete te overschrijven.

```PowerShell
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

In dit voorbeeld wordt de actie PostvakLogin-eigenaar toegevoegd aan de laura@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

In dit voorbeeld wordt de gemachtigde actie MoveToDeletedItems voor het postvak Teamdiscussie verwijderd.

```PowerShell
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

Ongeacht de methode die u gebruikt, heeft het aanpassen van de gecontroleerde postvakacties voor gebruikerspostvakken of gedeelde postvakken de volgende resultaten:

- Voor het aanmeldingstype dat u hebt aangepast, worden de gecontroleerde postvakacties niet meer beheerd door Microsoft.
- Het aanmeldingstype dat u hebt aangepast, wordt niet meer weergegeven in de eigenschap *DefaultAuditSet* voor het postvak, zoals [eerder beschreven.](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)

### <a name="restore-the-default-mailbox-actions"></a>De standaardpostvakacties herstellen

> [!NOTE]
> De volgende procedures zijn niet van toepassing op Microsoft 365 Groepspostvakken (ze zijn beperkt tot de standaardacties zoals hier [beschreven).](#mailbox-actions-for-microsoft-365-group-mailboxes)

Als u de postvakacties hebt aangepast die worden gecontroleerd op een gebruikerspostvak of een gedeeld postvak, kunt u de standaardpostvakacties voor een of alle aanmeldingstypen herstellen met behulp van deze syntaxis:

```PowerShell
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

U kunt meerdere *DefaultAuditSet-waarden* opgeven, gescheiden door komma's

In dit voorbeeld worden de standaard gecontroleerde postvakacties voor alle aanmeldingstypen op het postvak mark@contoso.onmicrosoft.com.

```PowerShell
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

In dit voorbeeld worden de standaard gecontroleerde postvakacties voor het aanmeldingstype Beheerder op het postvak chris@contoso.onmicrosoft.com hersteld, maar blijven de aangepaste gecontroleerde postvakacties voor de aanmeldingstypen Gemachtigde en Eigenaar over.

```PowerShell
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

Het herstellen van de standaard gecontroleerde postvakacties voor een aanmeldingstype heeft de volgende resultaten:

- De huidige lijst met postvakacties wordt vervangen door de standaardpostvakacties voor het aanmeldingstype.
- Nieuwe postvakacties die door Microsoft worden uitgebracht, worden automatisch toegevoegd aan de lijst met gecontroleerde acties voor het aanmeldingstype.
- De *eigenschap DefaultAuditSet* voor het postvak wordt bijgewerkt met het herstelde aanmeldingstype.

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>Postvakcontrole standaard uitschakelen voor uw organisatie

U kunt het controleren van postvakken standaard uitschakelen voor uw hele organisatie door de volgende opdracht uit te voeren in Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $true
```

Het standaard uitschakelen van postvakcontrole heeft de volgende resultaten:

- Postvakcontrole is uitgeschakeld voor uw organisatie.
- Vanaf het moment dat u postvakcontrole standaard hebt uitgeschakeld, worden er geen postvakacties gecontroleerd, zelfs niet als auditing is ingeschakeld in een postvak (de eigenschap *AuditEnabled* in het postvak is **Waar).**
- Postvakcontrole is niet ingeschakeld voor nieuwe postvakken en het instellen van de eigenschap *AuditEnabled* op een nieuw of bestaand postvak op **Waar** wordt genegeerd.
- Alle instellingen voor het omzeilen van een postvakcontrole (geconfigureerd met de **cmdlet Set-MailboxAuditBypassAssociation)** worden genegeerd.
- Bestaande postvakauditrecords blijven behouden totdat de leeftijdslimiet voor het auditlogboek voor de record verloopt.

### <a name="turn-on-mailbox-auditing-on-by-default"></a>Postvakcontrole standaard in-

Als u het controleren van postvakken voor uw organisatie weer wilt in- en uit te voeren, voer u de volgende opdracht uit in Exchange Online PowerShell:

```PowerShell
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>Logboekregistratie voor postvakcontrole omzeilen

Momenteel kunt u het controleren van postvakken voor specifieke postvakken niet uitschakelen wanneer postvakcontrole standaard is ingeschakeld in uw organisatie. Het instellen van de *eigenschap AuditEnabled-postvak* op **Onwaar** wordt bijvoorbeeld genegeerd.

U kunt echter nog steeds de cmdlet **Set-MailboxAuditBypassAssociation** in  Exchange Online PowerShell gebruiken om te voorkomen dat alle postvakacties van de opgegeven gebruikers worden vastgelegd, ongeacht waar de acties plaatsvinden. Bijvoorbeeld:

- Acties van postvakeigenaars die door de omzeilde gebruikers worden uitgevoerd, worden niet geregistreerd.
- Gemachtigde acties van de overgeslagen gebruikers in postvakken van andere gebruikers (inclusief gedeelde postvakken) worden niet geregistreerd.
- Beheeracties die door de omzeilde gebruikers worden uitgevoerd, worden niet geregistreerd.

Als u controlelogboekregistratie voor postvakken voor een specifieke gebruiker wilt omzeilen, vervangt u de naam, het e-mailadres, de alias of de gebruikersnaam van de gebruiker en voer u de volgende opdracht \<MailboxIdentity\> uit:

```PowerShell
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

Voer de volgende opdracht uit om te controleren of de controle voor de opgegeven gebruiker wordt overgeslagen:

```PowerShell
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

De waarde **Waar** geeft aan dat de logboekregistratie voor postvakcontrole wordt overgeslagen voor de gebruiker.

## <a name="more-information"></a>Meer informatie

- Hoewel logboekregistratie voor postvakaudit standaard is ingeschakeld voor alle organisaties, worden standaard alleen gebruikers met E5-licenties in auditlogboekgebeurtenissen in auditlogboekzoekingen in het [Beveiligings- & Compliancecentrum of](search-the-audit-log-in-security-and-compliance.md) via de API voor [beheeractiviteit van Office 365](/office/office-365-management-api/office-365-management-activity-api-reference) retourneren. 

  Als u postvakcontrolelogboekgegevens wilt ophalen voor gebruikers zonder E5-licenties, kunt u het volgende doen:

  - Postvakcontrole handmatig inschakelen voor afzonderlijke postvakken (voer de opdracht uit, `Set-Mailbox -Identity <MailboxIdentity> -AuditEnabled $true` ). Nadat u dit hebt uitgevoerd, kunt u auditlogboekzoekingen gebruiken in het Beveiligings- & compliancecentrum of via de Office 365 Management Activity API.
  
    > [!NOTE]
    > Als het controleren van postvakken al lijkt te zijn ingeschakeld in het postvak, maar uw zoekopdrachten geen resultaten retourneren, wijzigt u de waarde van de parameter _AuditEnabled_ in en vervolgens terug `$false` naar `$true` .
  
  - Gebruik de volgende cmdlets in Exchange Online PowerShell:
    - [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) om het auditlogboek van het postvak te doorzoeken op specifieke gebruikers.
    - [New-MailboxAuditLogSearch](/powershell/module/exchange/new-mailboxauditlogsearch) om het auditlogboek voor postvakken te doorzoeken op specifieke gebruikers en om de resultaten via e-mail naar opgegeven geadresseerden te laten verzenden.

  - Gebruik het Exchange -beheercentrum (EAC) in Exchange Online om de volgende acties uit te voeren:
    - [Auditlogboeken voor postvakken exporteren](/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)
    - [Een rapport postvaktoegang van een niet-eigenaar uitvoeren](/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- Standaard worden auditlogboekrecords voor postvakken 90 dagen bewaard voordat ze worden verwijderd. U kunt de leeftijdslimiet voor auditlogboekrecords wijzigen met  de parameter *AuditLogAgeLimit* op de cmdlet Postvak instellen in Exchange Online PowerShell. Als u deze waarde echter wilt verhogen, kunt u niet zoeken naar gebeurtenissen die ouder zijn dan 90 dagen in het auditlogboek.

  Als u de leeftijdslimiet verhoogt, moet u de cmdlet [Search-MailboxAuditLog](/powershell/module/exchange/search-mailboxauditlog) in Exchange Online PowerShell gebruiken om in het auditlogboek van het postvak van de gebruiker te zoeken naar records die ouder zijn dan 90 dagen.

- Als u de eigenschap *AuditLogAgeLimit* hebt gewijzigd voor een postvak dat standaard is ingeschakeld voor organisatie, wordt de bestaande leeftijdslimiet voor het auditlogboek niet gewijzigd. Met andere woorden: het standaard controleren van postvakken heeft geen invloed op de huidige leeftijdslimiet voor postvakauditrecords.

- Als u de *waarde AuditLogAgeLimit* in een Microsoft 365 groep wilt wijzigen, moet u de schakelknop opnemen in de `-GroupMailbox` opdracht **Postvak** instellen.

- Auditlogboekrecords voor postvakken worden opgeslagen in een submap (met de naam *Audits)* in de map Herstelbare items in het postvak van elke gebruiker. Houd rekening met de volgende zaken over postvakcontrolerecords en de map Herstelbare items:

  - Postvakauditrecords tellen mee voor het opslagquotum van de map Herstelbare items, die standaard 30 GB is (het waarschuwingsquotum is 20 GB). Het opslagquotum wordt automatisch verhoogd tot 100 GB (met een waarschuwingsquotum van 90 GB) wanneer:
    - Er wordt een wacht op een postvak geplaatst.
    - Het postvak is toegewezen aan een bewaarbeleid in het Compliancecentrum.

  - Controlerecords voor postvakken tellen ook mee voor [de maplimiet voor de map Herstelbare items.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits) In de submap Audits kunnen maximaal 3 miljoen items (auditrecords) worden opgeslagen.

    > [!NOTE]
    > Het is onwaarschijnlijk dat postvakcontrole standaard van invloed is op het opslagquotum of de maplimiet voor de map Herstelbare items.

    - U kunt de volgende opdracht uitvoeren in Exchange Online PowerShell om de grootte en het aantal items weer te geven in de submap Audits in de map Herstelbare items:

      ```PowerShell
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - U kunt een auditlogboekrecord niet rechtstreeks openen in de map Herstelbare items. in plaats daarvan gebruikt u de **cmdlet Search-MailboxAuditLog** of zoekt u in het auditlogboek om controlerecords voor postvakken te zoeken en weer te geven.

- Als een postvak in bewaring wordt geplaatst of is toegewezen aan een bewaarbeleid in het Compliancecentrum, worden auditlogboekrecords nog steeds bewaard voor de duur die is gedefinieerd door de *eigenschap AuditLogAgeLimit* van het postvak (standaard 90 dagen). Als u auditlogboekrecords langer wilt bewaren voor postvakken in de wachtstand, moet u de *waarde AuditLogAgeLimit* van het postvak verhogen.

- In een multi-geo-omgeving wordt cross-geopostvakcontrole niet ondersteund. Als een gebruiker bijvoorbeeld machtigingen krijgt toegewezen voor toegang tot een gedeeld postvak op een andere geografische locatie, worden postvakacties die door die gebruiker worden uitgevoerd, niet aangemeld in het postvakauditlogboek van het gedeelde postvak.
