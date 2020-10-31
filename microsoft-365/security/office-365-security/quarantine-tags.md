---
title: Quarantaine Tags
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Beheerders kunnen meer informatie over het gebruik van quarantaine-Tags om te bepalen wat gebruikers kunnen doen met hun Quarantine-berichten.
ms.openlocfilehash: 557a6832807c1768f482e76c76c0e92b027e49a7
ms.sourcegitcommit: 2810d1347e5016412074b2dd18e654aee7e593de
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/31/2020
ms.locfileid: "48819176"
---
# <a name="quarantine-tags"></a>Quarantaine Tags

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn momenteel in de preview-versie, zijn niet beschikbaar voor iedereen en kunnen worden gewijzigd.

Met quarantaine-labels in Exchange Online Protection (EOP) kunnen beheerders aangeven wat gebruikers kunnen doen met hun Quarantine-berichten op basis van de ontvangst van het bericht in quarantaine.

EOP is traditioneel toegestaan of voorkomen dat bepaalde niveaus van interactiviteit voor berichten in [quarantaine](find-and-release-quarantined-messages-as-a-user.md) en [spam meldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md)zijn toegestaan. Eindgebruikers kunnen bijvoorbeeld berichten weergeven en vrijgeven die zijn gequarantined via antispam filteren als spam of bulksgewijs, maar ze kunnen geen berichten weergeven of vrijgeven die zijn gequarantined als phishing met een hoge betrouwbaarheid.

Voor [ondersteunde beveiligingsfuncties](#step-2-assign-a-quarantine-tag-to-supported-features)opgeven welke gebruikers e-mail meldingen voor eindgebruikers mogen doen en in hun quarantaine berichten in quarantaine (berichten waarbij de gebruiker een geadresseerde is). Standaard wordt er automatisch quarantaine Tags toegewezen voor het afdwingen van de historische mogelijkheden voor eindgebruikers van berichten in quarantaine. U kunt ook aangepaste quarantaine Tags maken en toewijzen om te voorkomen dat eindgebruikers bepaalde acties op quarantaine berichten uitvoeren.

De afzonderlijke machtigingen worden gecombineerd in de volgende vooraf ingestelde machtigingsgroepen:

- Geen toegang
- Beperkte toegang
- Volledige toegang

De beschikbare afzonderlijke machtigingen en de beschikbare afzonderlijke machtigingen in de vooraf ingestelde machtigingsgroepen worden beschreven in de volgende tabel:

|Machtigingsset|Geen toegang|Beperkte toegang|Volledige toegang|
|---|:---:|:---:|:---:|
|**Afzender toestaan** ( _PermissionToAllowSender_ )|||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Afzender blokkeren** ( _PermissionToBlockSender_ )||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Delete** ( _PermissionToDelete_ )||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Voorbeeld** ( _PermissionToPreview_ )||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Toestaan dat geadresseerden een bericht uit Quarantine vrijgeven** ( _PermissionToRelease_ )|||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Toestaan dat geadresseerden een bericht aanvragen om te worden vrijgegeven uit Quarantine** ( _PermissionToRequestRelease_ )||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

Als u de standaardmachtigingen in de vooraf ingestelde machtigingsgroepen niet bevalt, kunt u aangepaste machtigingen gebruiken wanneer u aangepaste quarantaine Tags maakt of wijzigt. Zie voor meer informatie over wat u doet met de machtiging de sectie Machtigingen voor quarantaine voor de [quarantaine-label](#quarantine-tag-permission-details) verderop in dit artikel.

U maakt en wijst quarantaine tags toe in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken van Exchange Online; zelfstandige EOP PowerShell in EOP-organisaties zonder postvakken van Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina met **quarantaine Tags** wilt gaan, opent u deze <https://protection.office.com/quarantineTags> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Als u quarantaine codes wilt weergeven, wijzigen of verwijderen, moet u lid zijn van een van de volgende groepen rollen:
  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>Stap 1: quarantaine Tags maken in de beveiligings & nalevings centrum

1. Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \> **Policy** en selecteer vervolgens **quarantaine Tags** .

2. Selecteer op de pagina **Quarantine-Tags** de optie **aangepaste tag toevoegen** .

3. De wizard **nieuwe code** wordt geopend. Voer op de pagina **labelnaam** een korte maar unieke naam in het veld **labelnaam** in. U moet de tag op naam identificeren en selecteren in de komende stappen. Wanneer u klaar bent, klikt u op **volgende** .

4. Selecteer op de pagina **bericht toegang voor geadresseerde** een van de volgende waarden:
   - **Geen toegang**
   - **Beperkte toegang**
   - **Volledige toegang**

   Eerder in dit artikel worden de afzonderlijke machtigingen van deze machtigingsgroepen beschreven.

   Als u aangepaste machtigingen wilt opgeven, selecteert u **specifieke toegang instellen (Geavanceerd)** en configureert u de volgende instellingen:

     - **Selecteer voorkeur van release actie** : Selecteer een van de volgende waarden:
       - **Geen uitgave actie** : dit is de standaardwaarde.
       - **Toestaan dat geadresseerden een bericht uit Quarantine vrijgeven**
       - **Toestaan dat geadresseerden een bericht aanvragen om te worden vrijgegeven uit Quarantine**

     - **Selecteer extra acties geadresseerden kunnen berichten in quarantaine plaatsen** : Selecteer enkele, alle of geen van de volgende waarden:
       - **Wissen**
       - **Voorbeeld**
       - **Afzender toestaan**
       - **Afzender blokkeren**

   Deze machtigingen en hun effect op quarantaine berichten en de spam meldingen van eindgebruikers worden beschreven in de sectie [machtigingsgegevens van Quarantine](#quarantine-tag-permission-details) voor de tag verderop in dit artikel.

   Wanneer u klaar bent, klikt u op **volgende** .

5. Controleer de instellingen op de pagina **overzicht** die wordt weergegeven. U kunt op de verschillende instellingen klikken om de **bewerking** te wijzigen.

   Als u klaar bent, klikt u op **verzenden** .

6. Op de bevestigingspagina die verschijnt, klikt u op **gereed** .

U bent nu klaar om de code van Quarantine toe te wijzen aan een Quarantine-functie, zoals wordt beschreven in de sectie [stap 2](#step-2-assign-a-quarantine-tag-to-supported-features) .

### <a name="create-quarantine-tags-in-powershell"></a>Quarantaine Tags maken in PowerShell

Als u liever PowerShell gebruikt voor het maken van quarantaine Tags, maakt u verbinding met Exchange Online PowerShell of Exchange Online Protection PowerShell en gebruikt u de **nieuwe QuarantineTag-** cmdlet. U kunt kiezen uit twee verschillende methoden:

- Gebruik de parameter _EndUserQuarantinePermissionsValue_ .
- Gebruik de parameter _EndUserQuarantinePermissions_ .

In de volgende secties wordt beschreven welke methoden worden beschreven.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>De parameter EndUserQuarantinePermissionsValue gebruiken

Gebruik de volgende syntaxis om een Quarantine-tag te maken met behulp van de parameter _EndUserQuarantinePermissionsValue_ :

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

De parameter _EndUserQuarantinePermissionsValue_ gebruikt een decimale waarde die wordt geconverteerd van een binaire waarde. De binaire waarde komt overeen met de beschikbare Quarantine-machtigingen voor eindgebruikers in een specifieke volgorde. Voor elke machtiging is de waarde 1 gelijk aan waar en is de waarde 0 gelijk aan false.

In de volgende tabel vindt u een beschrijving van de vereiste volgorde en waarden voor elke afzonderlijke machtiging in vooraf ingestelde machtigingsgroepen:

****

|Machtigingsset|Geen toegang|Beperkte toegang|Volledige toegang|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|0|0|1|
|PermissionToBlockSender|0|1|1|
|PermissionToDelete|0|1|1|
|PermissionToDownload<sup>\*</sup>|0|0|0|
|PermissionToPreview|0|1|1|
|PermissionToRelease<sup>\*\*</sup>|0|0|1|
|PermissionToRequestRelease<sup>\*\*</sup>|0|1|0|
|PermissionToViewHeader<sup>\*</sup>|0|0|0|
|Binaire waarde|00000000|01101010|11101100|
|Te gebruiken decimale waarde|0|106|236|

<sup>\*</sup> Deze waarde is op dit moment altijd 0. Voor PermissionToViewHeader wordt met de waarde 0 de knop berichtkop **weergeven** niet verborgen voor de details van het gequarantinee bericht (de knop is altijd beschikbaar).

<sup>\*\*</sup> Stel niet beide waarden in op 1. Stel een in op 1 en de andere 0, of stel deze in op 0.

In het volgende voorbeeld wordt de nieuwe naam van de naam van de Quarantine-tag geopend en worden de machtigingen geen toegang toegewezen, zoals beschreven in de vorige tabel.

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

Gebruik voor machtigingen voor beperkte toegang de waarde 106. Gebruik voor volledige toegangsmachtigingen de waarde 236.

Gebruik voor aangepaste machtigingen de eerdere tabel voor de binaire waarde die overeenkomt met de gewenste machtigingen. Converteer de binaire waarde naar een decimale waarde en gebruik de decimale waarde voor de parameter _EndUserQuarantinePermissionsValue_ .

Zie [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)voor gedetailleerde syntaxis-en parameterinformatie.

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>De parameter EndUserQuarantinePermissions gebruiken

Voer de volgende stappen uit om een Quarantine-tag te maken met behulp van de parameter _EndUserQuarantinePermissionsValue_ :

Een. Een quarantaine machtigingen object in een variabele opslaan met de **nieuwe QuarantinePermissions-** cmdlet.
<br/>
BB. Gebruik de variabele als _EndUserQuarantinePermissions_ waarde in de opdracht **New-QuarantineTag** .

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>Stap A: een quarantaine machtigingen object opslaan in een variabele

Gebruik de volgende syntaxis:

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

De standaardwaarde voor ongebruikte parameters is `$false` , dus u hoeft de parameters alleen te gebruiken waarvoor u een waarde wilt instellen `$true` .

In de volgende voorbeelden ziet u hoe u machtigingsobjecten kunt maken die overeenkomen met de vooraf ingestelde machtigingsgroepen:

- **Geen toegang** :

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **Beperkte toegang** :

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **Volledige toegang** :

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

Als u de waarden wilt weergeven die u hebt ingesteld, voert u de variabele naam uit als een opdracht (bijvoorbeeld de opdracht uitvoeren `$NoAccess` ).

Stel voor aangepaste machtigingen de parameters _PermissionToRelease_ en _PermissionToRequestRelease_ niet in op `$true` . Stel een in `$true` en sluit het `$false` af, of houd beide ingedrukt `$false` .

U kunt ook een bestaande machtigings objectvariabele wijzigen nadat u deze hebt gemaakt, maar voordat u deze gebruikt met behulp van de cmdlet **set-QuarantinePermissions** .

Zie [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) en [set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)voor gedetailleerde syntaxis-en parameterinformatie.

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>Stap B: gebruik de variabele in de opdracht New-QuarantineTag

Nadat u het object permissions hebt gemaakt en opgeslagen in een variabele, gebruikt u de variabele voor de waarde van de _EndUserQuarantinePermission_ -parameter in de volgende opdracht **New-QuarantineTag** :

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

In dit voorbeeld wordt een nieuwe Quarantine-tag met de naam LimitedAccess gemaakt met behulp van het `$LimitedAccess` machtigingen object dat in de vorige stap is beschreven en gemaakt.

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

Zie [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>Stap 2: een quarantaine-tag toewijzen aan ondersteunde functies

In _ondersteunde_ beveiligingsfuncties waarmee u berichten of bestanden (automatisch of als configureerbare actie) kunt toewijzen, kunt u een Quarantine-tag toewijzen aan de beschikbare quarantaine acties. In de volgende tabel vindt u een beschrijving van de functies voor quarantaine en de beschikbaarheid van quarantaine Tags:

****

|Functie|Ondersteunde labels voor quarantaine?|Standaard gebruikte quarantaine Tags|
|---|:---:|---|
|[Anti spam beleid](configure-your-spam-filter-policies.md): <ul><li>**Spam** ( _SpamAction_ )</li><li>**Hoge betrouwbaarheid spam** ( _HighConfidenceSpamAction_ )</li><li>**Malafide e-mailadres** ( _PhishSpamAction_ )</li><li>**E-mail met malafide vertrouwens kwaliteit** ( _HighConfidencePhishAction_ )</li><li>**Bulk-e-mail** ( _BulkSpamAction_ )</li></ul>|Ja|<ul><li>DefaultSpamTag (volledige toegang)</li><li>DefaultHighConfSpamTag (volledige toegang)</li><li>DefaultPhishTag (volledige toegang)</li><li>DefaultHighConfPhishTag (geen toegang)</li><li>DefaultBulkTag (volledige toegang)</li></ul>
|Anti malafide beleid: <ul><li>[Spoof Intelligence-bescherming](set-up-anti-phishing-policies.md#spoof-settings) ( _AuthenticationFailAction_ )</li><li>[Imitatie bescherming](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies):<sup>\*</sup> <ul><li>**E-mail wordt verzonden door een geïmiteerde gebruiker** ( _TargetedUserProtectionAction_ )</li><li>**E-mail wordt verzonden door een geïmiteerd domein** ( _TargetedDomainProtectionAction_ )</li><li>**Postvak intelligentie** \> **E-mail wordt verzonden door een geïmiteerde gebruiker** ( _MailboxIntelligenceProtectionAction_ )</li></ul></li></ul></ul>|Nee|n/b|
|[Beleid voor anti-malware](configure-anti-malware-policies.md): alle gevonden berichten worden altijd in quarantaine geplaatst.|Nee|n/b|
|[ATP voor SharePoint, OneDrive en Microsoft Teams](atp-for-spo-odb-and-teams.md)|Nee|n/b|
|Voor [e-mail stroom regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transport-regels genoemd) met de actie: **Bezorg het bericht in de gehoste quarantaine** ( _quarantaine_ ).|Nee|n/b|
|

<sup>\*</sup> De instellingen voor imitatie beveiliging zijn alleen beschikbaar in Microsoft Defender voor Office 365.

Als u tevreden bent met de machtigingen voor eindgebruikers van de standaard Quarantine-Tags, hoeft u niets te doen. Als u de capaciteiten van de eindgebruikers wilt aanpassen (beschikbare knoppen) in spam meldingen voor eindgebruikers of in het ontvangen van Details van een bericht, kunt u een aangepaste Quarantine-markering toewijzen.

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>Quarantaine tags toewijzen in Antispambeleid in de beveiligings & nalevings centrum

Volledige instructies voor het maken en wijzigen van anti-spam beleid vindt u in het onderwerp [Antispambeleid in EOP](configure-your-spam-filter-policies.md).

1. Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \> **Policy** \> en selecteer vervolgens **anti spam** . Of open <https://protection.office.com/antispam> .

2. Zoek en selecteer een bestaand Antispambeleid om dit te bewerken, of maak een nieuw anti-spam beleid.

3. Ga in het vervolgmenu met beleidsdetails naar het gedeelte **spam-en Bulkacties** .
  
4. Als u **quarantaine bericht** hebt geselecteerd voor de actie van een beschikbare spamfilter Verdict, is het dialoogvenster **quarantainebeleid toepassen** beschikbaar voor het selecteren van de Quarantine-tag voor die Verdict.

   **Opmerking** : wanneer u een nieuw beleid maakt, wordt er een lege Quarantine-label waarde voor een spam filterd verdict aangegeven Wanneer u de beleidsregels later bewerkt, worden de lege waarden vervangen door de werkelijke namen van de werkelijke namen van quarantaine Tags, zoals beschreven in de vorige tabel.
  
   ![Selectie van quarantaine-Tags in een Antispambeleid](../../media/quarantine-tags-in-anti-spam-policies.png)

5. Klik op **Opslaan** wanneer u gereed bent.

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>Quarantaine tags toewijzen in Antispambeleid in PowerShell

Als u liever PowerShell gebruikt om quarantaine tags toe te wijzen in Antispambeleid, maakt u verbinding met Exchange Online PowerShell of Exchange Online Protection PowerShell en gebruikt u de volgende syntaxis:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Opmerkingen** :

- De standaardwaarde voor de _HighConfidencePhishAction_ -parameter is Quarantine, dus u hoeft de Quarantine-actie niet in te stellen voor de detectie van hoge betrouwbaarheid in nieuwe antispambeleid. Voor alle andere Verdicts voor spamfilters in een nieuw of bestaand Antispambeleid, is de quarantaine-tag alleen van kracht als de actiewaarde Quarantine is. Voer de volgende opdracht uit als u de actiewaarden wilt weergeven in een bestaand Antispambeleid:

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  Zie [EOP antispam beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)voor informatie over de standaardactie waarden en de aanbevolen actiewaarden voor de standaard en strikte.

- Een spam filtering verdict zonder een bijbehorende Quarantine-label parameter betekent de [standaard Quarantine-tag](#step-2-assign-a-quarantine-tag-to-supported-features) voor dat verdict wordt gebruikt.

  U hoeft alleen de standaardindeling van Quarantine te vervangen door een aangepaste Quarantine-tag als u de standaardfuncties voor eindgebruikers van quarantaine berichten wilt wijzigen.

- Voor een nieuw Antispambeleid in PowerShell is een spamfilter beleid vereist met behulp van de **New-HostedContentFilterPolicy** -cmdlet en een nieuwe regel voor spamfilter (Recipient filters) met behulp van de **New-HostedContentFilterRule-** cmdlet. Zie [PowerShell gebruiken om Antispambeleid te maken](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)voor instructies.

In dit voorbeeld wordt een nieuw beleid voor het filteren van ongewenste e-mail gemaakt met de volgende instellingen:

- De actie voor alle spam filtering Verdicts is ingesteld op Quarantine.
- De aangepaste map met de naam waartoe **geen toegangsrechten wordt** toegewezen, vervangt standaard Quarantine Tags waaraan geen **toegangs** machtigingen zijn toegewezen.

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

Zie [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

In dit voorbeeld wordt het bestaande spamfilter beleid met de naam Human resources gewijzigd. De actie voor de spam Quarantine verdict is ingesteld op Quarantine en de aangepaste Quarantine-tag heeft de naam toegang toegewezen.

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

Zie [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>Instellingen voor globaal Quarantine-meldingen configureren in het beveiligings & nalevings centrum

Met de algemene instellingen voor quarantaine Tags kunt u de spam meldingen voor eindgebruikers aanpassen die worden verzonden naar geadresseerden van berichten die zijn gequarantined. Voor meer informatie over deze meldingen raadpleegt u [spam meldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \> **Policy** en selecteer vervolgens **quarantaine Tags** .

2. Selecteer op de pagina **Quarantine-Tags** de optie **globale instellingen** .

3. Configureer enkele of alle van de volgende instellingen in het vervolgmenu met **instellingen voor Quarantine-meldingen** dat wordt geopend:

   - **Mijn bedrijfslogo gebruiken** : Selecteer deze optie om het standaardlogo van Microsoft te vervangen dat wordt gebruikt voor spam meldingen voor eindgebruikers. Voordat u dit doet, moet u de instructies volgen in [het Microsoft 365-thema aanpassen voor uw organisatie](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) om het aangepaste logo te uploaden.

     In de volgende schermafbeelding ziet u een aangepast logo in een spam melding voor eindgebruikers:

     ![Een aangepast logo in een melding voor spam van eindgebruikers](../../media/quarantine-tags-esn-customization-logo.png)

   - **Taal kiezen** : spam meldingen voor eindgebruikers zijn al gelokaliseerd op basis van de taalinstellingen van de geadresseerde. U kunt aangepaste tekst in verschillende talen opgeven voor de **weergavenaam** en de **vrijwarings** waarden.

     Selecteer minimaal één taal in het vak voor de eerste taal en klik op **toevoegen** . U kunt meerdere talen selecteren door op **toevoegen** te klikken. Een vak van de sectie taal bevat alle talen die u hebt geselecteerd:

     ![Geselecteerde talen in het tweede vak van de taal in de instellingen voor algemeen Quarantine-meldingen van quarantaine markeringen](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **Weergavenaam** : de weergavenaam van de afzender aanpassen die wordt gebruikt voor spam meldingen voor eindgebruikers.

     Voor elke taal die u hebt toegevoegd, selecteert u de taal in het tweede vak taal (niet op de X) en typt u de gewenste tekstwaarde in het vak **weergavenaam** .

     In de volgende schermafbeelding wordt de aangepaste weergavenaam weergegeven in een spam melding voor eindgebruikers:

     ![Een aangepaste weergavenaam van de afzender in een spam melding voor eindgebruikers](../../media/quarantine-tags-esn-customization-display-name.png)

   - **Vrijwaring** : een aangepaste Disclaimer toevoegen aan de onderkant van spam meldingen voor eindgebruikers. De gelokaliseerde tekst, **een afwijzing van uw organisatie:** wordt altijd eerst opgenomen, gevolgd door de tekst die u opgeeft.

     Voor elke taal die u hebt toegevoegd, selecteert u de taal in het tweede vak taal (niet op de X) en typt u de gewenste tekstwaarde in het vak **Disclaimer** .

     In de volgende schermafbeelding ziet u de aangepaste disclaimer in een melding voor spam van eindgebruikers:

     ![Een aangepaste Disclaimer onder aan een spam melding voor eindgebruikers](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>Quarantaine tags weergeven in het beveiligings & nalevings centrum

1. Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \> **Policy** en selecteer vervolgens **quarantaine Tags** .

- Als u de instellingen van ingebouwde of aangepaste Quarantine-tags wilt bekijken, selecteert u de quarantaine-tag in de lijst (niet het selectievakje inschakelen).

- Als u de algemene instellingen wilt bekijken, selecteert u **algemene instellingen**

### <a name="view-quarantine-tags-in-powershell"></a>Quarantaine-markeringen weergeven in PowerShell

Voer een van de volgende stappen uit als u liever PowerShell gebruikt om quarantaine Tags weer te geven:

- Voer de volgende opdracht uit als u een overzichtslijst met alle ingebouwde of aangepaste tags wilt weergeven:

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- Als u de instellingen van ingebouwde of aangepaste Quarantine-tags wilt bekijken, vervangt u \<TagName\> de naam van de quarantaine-tag en voert u de volgende opdracht uit:

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- Voer de volgende opdracht uit om de algemene instellingen weer te geven:

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

Zie [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>Quarantaine markeringen verwijderen in het beveiligings & nalevings centrum

**Opmerkingen** :

- U kunt ingebouwde Quarantine-Tags niet verwijderen.

- Voordat u een aangepaste Quarantine-tag verwijdert, controleert u of deze niet wordt gebruikt. Voer bijvoorbeeld de volgende opdracht uit in PowerShell:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  Als u de tag Quarantine gebruikt, moet u [de toegewezen quarantaine-tag vervangen](#step-2-assign-a-quarantine-tag-to-supported-features) voordat u deze verwijdert.

1. Ga in het beveiligings & compliance naar beleid voor **risicobeheer** \> **Policy** en selecteer vervolgens **quarantaine Tags** .

2. Selecteer op de pagina **Quarantine-Tags** de aangepaste Quarantine-tag die u wilt verwijderen en klik vervolgens op **markering verwijderen** .

3. Klik in het bevestigingsvenster dat wordt weergegeven op **tag verwijderen** .

### <a name="remove-quarantine-tags-in-powershell"></a>Quarantaine markeringen verwijderen in PowerShell

Als u liever PowerShell gebruikt om een aangepaste Quarantine-tag te verwijderen, vervangt u \<TagName\> de naam van de quarantaine-tag en voert u de volgende opdracht uit:

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

Zie [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="quarantine-tag-permission-details"></a>Details van een quarantaine label machtiging

In de volgende secties wordt de werking beschreven van vooraf ingestelde machtigingsgroepen en afzonderlijke machtigingen in de details van quarantaine berichten en spam meldingen voor eindgebruikers.

### <a name="preset-permissions-groups"></a>Vooraf ingestelde machtigingsgroepen

De afzonderlijke machtigingen in de vooraf ingestelde machtigingsgroepen worden weergegeven in de tabel aan het begin van dit artikel.

#### <a name="no-access"></a>Geen toegang

Als u in het deel van de Quarantine de machtigingen **geen toegangs** rechten (geen machtigingen) toewijst, krijgen gebruikers nog enkele basismogelijkheden:

- **Details van quarantaine berichten** : de knop **koptekst van bericht weergeven** is altijd beschikbaar.

  ![De beschikbare knoppen in de details van het gequarantinete bericht als met het quarantaine-label de gebruiker geen toegang heeft](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **Meldingen voor spam van eindgebruikers** : de knop **controleren** waarmee de gebruiker het bericht in quarantaine afneemt is altijd beschikbaar.

  ![Beschikbare knoppen in de melding voor spam van eindgebruikers als met het quarantaine-label de gebruiker geen toegang heeft](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>Beperkte toegang

Als het Quarantine-label de machtigingen voor **beperkte toegang** toewijst, krijgen gebruikers de volgende mogelijkheden:

- **Details van quarantaine bericht** : de volgende knoppen zijn beschikbaar:
  - **Release aanvragen**
  - **Koptekst van bericht weergeven**
  - **Voorbeeld van bericht**
  - **Afzender blokkeren**
  - **Uit quarantaine verwijderen**

  ![De beschikbare knoppen in de details van het gequarantinete bericht als de quarantaine-tag de gebruikers beperkte toegangsmachtigingen geeft](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **Spam meldingen voor eindgebruikers** : de volgende knoppen zijn beschikbaar:
  - **Afzender blokkeren**
  - **Gereviseerd**

  ![Beschikbare knoppen in de melding voor spam van eindgebruikers als met het quarantaine-label de gebruikers beperkte toegangsmachtigingen](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>Volledige toegang

Als het Quarantine-label de **volledige toegangs** machtigingen (alle beschikbare machtigingen) toewijst, krijgen gebruikers de volgende mogelijkheden:

- **Details van quarantaine bericht** : de volgende knoppen zijn beschikbaar:
  - **Bericht uitbrengen**
  - **Koptekst van bericht weergeven**
  - **Voorbeeld van bericht**
  - **Afzender blokkeren**
  - **Afzender toestaan**
  - **Uit quarantaine verwijderen**

  ![De beschikbare knoppen in de details van het gequarantinete bericht als de Quarantine-tag de gebruiker volledige toegangsmachtigingen geeft](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **Spam meldingen voor eindgebruikers** : de volgende knoppen zijn beschikbaar:
  - **Afzender blokkeren**
  - **Release**
  - **Gereviseerd**

  ![Beschikbare knoppen in de melding voor spam van eindgebruikers als met de tag Quarantine de gebruiker volledige toegangsmachtigingen geeft](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>Afzonderlijke machtigingen

> [!NOTE]
> Let op: gebruikers krijgen altijd de knoppen die worden beschreven in de sectie [geen toegang](#no-access) . Deze knoppen zijn niet opgenomen in de afzonderlijke beschrijvingen van machtigingen.

#### <a name="allow-sender-permission"></a>Toestemming voor afzender toestaan

Met de machtiging **afzender toestaan** ( _PermissionToAllowSender_ ) kunt u de toegang tot de knop beheren waarmee gebruikers de verzender van het gequarantinete bericht eenvoudig kunnen toevoegen aan hun lijst met veilige afzenders.

- **Details van quarantaine berichten** :
  - Toestemming voor **afzender toestaan** ingeschakeld: de knop **afzender toestaan** is beschikbaar.
  - Toestemming voor **afzender toestaan** uitgeschakeld: de knop **afzender toestaan** is niet beschikbaar.

- **Meldingen voor spam van eindgebruikers** : geen effect.

Zie voor meer informatie over de lijst met veilige afzenders de [Geblokkeerde afzenders verhinderen](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) en [Exchange Online PowerShell gebruiken voor het configureren van de veilige lijst-verzameling voor een postvak](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).

### <a name="block-sender-permission"></a>Machtigingen voor afzender blokkeren

Met de machtiging **afzender blokkeren** ( _PermissionToBlockSender_ ) kunt u de toegang tot de knop beheren waarmee gebruikers op de lijst met geblokkeerde afzenders in de lijst met geblokkeerde afzenders de juiste afzender kunnen toevoegen.

- **Details van quarantaine berichten** :
  - Machtigingen voor **afzender blokkeren** ingeschakeld: de knop **afzender blokkeren** is beschikbaar.
  - Toestemming voor **afzender blokkeren** uitgeschakeld: de knop **afzender blokkeren** is niet beschikbaar.

- **Spam meldingen voor eindgebruikers** :
  - Toestemming voor **afzender blokkeren** uitgeschakeld: de knop **afzender blokkeren** is niet beschikbaar.
  - Machtigingen voor **afzender blokkeren** ingeschakeld: de knop **afzender blokkeren** is beschikbaar.

Zie voor meer informatie over de lijst met geblokkeerde afzenders [berichten van iemand blokkeren](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) en [Exchange Online PowerShell gebruiken om de veilige lijst-verzameling te configureren voor een postvak](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).

### <a name="delete-permission"></a>Machtiging voor verwijderen

Met de machtiging **verwijderen** ( _PermissionToDelete_ ) kunt u gebruikers de mogelijkheid bieden hun berichten te verwijderen (berichten waarvan de gebruiker een geadresseerde is) uit Quarantine.

- **Details van quarantaine berichten** :
  - Machtigingen voor **verwijderen** ingeschakeld: de knop **verwijderen uit quarantaine** is beschikbaar.
  - **Verwijderen** machtiging uitgeschakeld: de knop **verwijderen uit quarantaine** is niet beschikbaar.

- **Meldingen voor spam van eindgebruikers** : geen effect.

### <a name="preview-permission"></a>Voorbeeld van machtiging

Met de machtiging **voorbeeld** ( _PermissionToPreview_ ) kunt u bepalen of gebruikers hun berichten in quarantaine weergeven.

- **Details van quarantaine berichten** :
  - **Voorbeeld** van machtigingen ingeschakeld: de knop **voorbeeld van bericht** is beschikbaar.
  - **Voorbeeld** van machtiging uitgeschakeld: de knop **voorbeeld van bericht** is niet beschikbaar.

- **Meldingen voor spam van eindgebruikers** : geen effect.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Toestaan dat geadresseerden een bericht uit quarantaine vrijgeven

Met de mogelijkheid om te zorgen dat de gebruikers van de **quarantaine machtiging een bericht vrijgeven** ( _PermissionToRelease_ ), kunt u de mogelijkheid van gebruikers de mogelijkheid bieden rechtstreeks hun berichten in quarantaine te brengen en zonder de goedkeuring van een beheerder.

- **Details van quarantaine berichten** :
  - Machtigingen ingeschakeld: de knop **bericht vrijgeven** is beschikbaar.
  - Machtiging uitgeschakeld: de knop **bericht vrijgeven** is niet beschikbaar.
  
- **Spam meldingen voor eindgebruikers** :
  - Machtigingen ingeschakeld: de knop **uitbrengen** is beschikbaar.
  - Machtiging uitgeschakeld: de knop **release** is niet beschikbaar.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Toestaan dat geadresseerden een bericht aanvragen om te worden vrijgegeven uit de quarantaine machtiging

De mogelijkheid van de _gebruikers om de_ vrijgave van de geplaatste berichten _PermissionToRequestRelease_ in te stellen, wordt bepaald door de mogelijkheid **dat geadresseerden een bericht aanvragen voor** de toegang tot de Quarantine. Het bericht wordt alleen vrijgegeven nadat een beheerder de aanvraag heeft goedgekeurd.

- **Details van quarantaine berichten** :
  - Machtigingen ingeschakeld: de knop **release aanvragen** is beschikbaar.
  - Machtiging uitgeschakeld: de knop **release aanvragen** is niet beschikbaar.

- **Meldingen voor spam van eindgebruikers** : de knop **uitbrengen** is niet beschikbaar.
