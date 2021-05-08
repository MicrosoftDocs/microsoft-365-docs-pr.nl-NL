---
title: Quarantainelabels
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Beheerders kunnen leren hoe ze quarantainelabels kunnen gebruiken om te bepalen wat gebruikers kunnen doen met hun in quarantaine geplaatste berichten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 512c589572502deacb5529ca9d6f2876861bf050
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274458"
---
# <a name="quarantine-tags"></a>Quarantainelabels

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn momenteel beschikbaar in Preview, zijn niet voor iedereen beschikbaar en kunnen worden gewijzigd.

Met quarantainelabels in Exchange Online Protection (EOP) kunnen beheerders bepalen wat gebruikers kunnen doen met hun in quarantaine geplaatste berichten op basis van de manier waarop het bericht in quarantaine is geplaatst.

EOP heeft vanouds bepaalde interactiviteitsniveaus toegestaan of voorkomen voor berichten in [quarantaine](find-and-release-quarantined-messages-as-a-user.md) en in [spammeldingen van eindgebruikers.](use-spam-notifications-to-release-and-report-quarantined-messages.md) Eindgebruikers kunnen bijvoorbeeld berichten bekijken en vrijgeven die in quarantaine zijn geplaatst door antispamfilters als spam of bulksgewijs, maar ze kunnen berichten die in quarantaine zijn geplaatst, niet weergeven of vrijgeven als phishing met veel vertrouwen.

Voor [ondersteunde](#step-2-assign-a-quarantine-tag-to-supported-features)beveiligingsfuncties geven quarantainelabels aan wat gebruikers mogen doen in spammeldingen van eindgebruikers en in hun in quarantaine geplaatste berichten in quarantaine (berichten waarbij de gebruiker een geadresseerde is). Standaard quarantainelabels worden automatisch toegewezen om de historische mogelijkheden voor eindgebruikers af te dwingen voor in quarantaine geplaatste berichten. U kunt ook aangepaste quarantainelabels maken en toewijzen om te voorkomen dat eindgebruikers specifieke acties uitvoeren op in quarantaine geplaatste berichten.

De afzonderlijke machtigingen worden gecombineerd in de volgende vooraf ingestelde machtigingsgroepen:

- Geen toegang
- Beperkte toegang
- Volledige toegang

De beschikbare afzonderlijke machtigingen en wat al dan niet is opgenomen in de vooraf ingestelde machtigingsgroepen, worden in de volgende tabel beschreven:

<br>

****

|Machtiging|Geen toegang|Beperkte toegang|Volledige toegang|
|---|:---:|:---:|:---:|
|**Afzender toestaan** (_PermissionToAllowSender_)|||![Vinkje](../../media/checkmark.png)|
|**Afzender blokkeren** (_PermissionToBlockSender_)||![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|**Verwijderen** (_PermissionToDelete_)||![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|**Preview** (_PermissionToPreview_)||![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|**Geadresseerden toestaan een bericht uit quarantaine te laten** gaan (_PermissionToRelease_)|||![Vinkje](../../media/checkmark.png)|
|**Ontvangers toestaan om een bericht uit quarantaine** te laten gaan (_PermissionToRequestRelease_)||![Vinkje](../../media/checkmark.png)||
|

Als de standaardmachtigingen in de vooraf ingestelde machtigingsgroepen u niet be staan, kunt u aangepaste machtigingen gebruiken wanneer u aangepaste quarantainelabels maakt of wijzigt. Zie de sectie Machtigingsgegevens voor [](#quarantine-tag-permission-details) quarantainelabels verder in dit artikel voor meer informatie over wat elke machtiging doet.

U maakt en wijst quarantainelabels toe in het Beveiligings- & Compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met Exchange Online-postvakken; zelfstandige EOP PowerShell in EOP-organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Quarantainelabels wilt** gaan, opent u <https://protection.office.com/quarantineTags> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Als u quarantainelabels wilt weergeven, maken, wijzigen of  verwijderen,  moet u lid zijn van de rollen Organisatiebeheer of Beveiligingsbeheerder in het [Beveiligings- & Compliancecentrum.](permissions-in-the-security-and-compliance-center.md)

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>Stap 1: Quarantainelabels maken in het beveiligings- & compliancecentrum

1. Ga in het & Compliancecentrum naar **Bedreigingsbeleid** \>  en selecteer vervolgens **Quarantainelabels.**

2. Selecteer op **de pagina Quarantainelabels** **de optie Aangepaste tag toevoegen.**

3. De **wizard Nieuwe tag** wordt geopend. Voer op **de pagina Tagnaam** een korte, maar unieke naam in het veld **Naam van** tag in. U moet de tag identificeren en selecteren op naam in de komende stappen. Wanneer u klaar bent, klikt u op **Volgende.**

4. Selecteer op **de pagina Berichttoegang** van geadresseerde een van de volgende waarden:
   - **Geen toegang**
   - **Beperkte toegang**
   - **Volledige toegang**

   De afzonderlijke machtigingen die in deze machtigingsgroepen zijn opgenomen, worden eerder in dit artikel beschreven.

   Als u aangepaste machtigingen wilt opgeven, **selecteert u Specifieke toegang instellen (Geavanceerd)** en configureert u de volgende instellingen:

     - **Selecteer releaseactievoorkeur**: Selecteer een van de volgende waarden:
       - **Geen releaseactie:** dit is de standaardwaarde.
       - **Geadresseerden toestaan een bericht uit quarantaine te plaatsen**
       - **Geadresseerden toestaan om een bericht uit quarantaine te laten worden geplaatst**

     - **Selecteer extra acties die geadresseerden kunnen uitvoeren op in quarantaine** geplaatste berichten: Selecteer enkele, alle of geen van de volgende waarden:
       - **Verwijderen**
       - **Voorbeeld**
       - **Afzender toestaan**
       - **Afzender blokkeren**

   Deze machtigingen en het effect ervan op in quarantaine geplaatste [](#quarantine-tag-permission-details) berichten en in spammeldingen van eindgebruikers worden beschreven in de sectie Machtigingsgegevens van quarantainelabels verder in dit artikel.

   Wanneer u klaar bent, klikt u op **Volgende.**

5. Controleer de **instellingen** op de pagina Overzicht die wordt weergegeven. U kunt op **Bewerken op elke** instelling klikken om deze te wijzigen.

   Wanneer u klaar bent, klikt u op **Verzenden.**

6. Klik **op Klaar** op de bevestigingspagina die wordt weergegeven.

U bent nu klaar om de quarantainetag toe te wijzen aan een quarantainefunctie, zoals beschreven in de sectie Stap [2.](#step-2-assign-a-quarantine-tag-to-supported-features)

### <a name="create-quarantine-tags-in-powershell"></a>Quarantainelabels maken in PowerShell

Als u Liever PowerShell gebruikt om quarantainelabels te maken, maakt u verbinding met Exchange Online PowerShell of Exchange Online Protection PowerShell en gebruikt u de **cmdlet New-QuarantineTag.** U kunt kiezen uit twee verschillende methoden:

- Gebruik de _parameter EndUserQuarantinePermissionsValue._
- Gebruik de _parameter EndUserQuarantinePermissions._

Deze methoden worden in de volgende secties beschreven.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>De parameter EndUserQuarantinePermissionsValue gebruiken

Als u een quarantainetag wilt maken met de parameter _EndUserQuarantinePermissionsValue,_ gebruikt u de volgende syntaxis:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

De _parameter EndUserQuarantinePermissionsValue_ gebruikt een decimale waarde die wordt geconverteerd van een binaire waarde. De binaire waarde komt overeen met de beschikbare quarantainemachtigingen voor eindgebruikers in een specifieke volgorde. Voor elke machtiging is de waarde 1 gelijk aan Waar en is de waarde 0 gelijk aan Onwaar.

De vereiste volgorde en waarden voor elke afzonderlijke machtiging in vooraf ingestelde machtigingsgroepen worden in de volgende tabel beschreven:

<br>

****

|Machtiging|Geen toegang|Beperkte toegang|Volledige toegang|
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
|Decimaal te gebruiken waarde|0|106|236|
|

<sup>\*</sup> Op dit moment is deze waarde altijd 0. Voor PermissionToViewHeader verbergt de waarde 0 de knop **Berichtkopweergave** niet in de details van het in quarantaine geplaatste bericht (de knop is altijd beschikbaar).

<sup>\*\*</sup> Stel beide waarden niet in op 1. Stel een op 1 en de andere in op 0 of stel beide in op 0.

In dit voorbeeld wordt een nieuwe naam van de quarantainetag NoAccess gemaakt die de machtiging Geen toegang toewijst, zoals beschreven in de vorige tabel.

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

Gebruik de waarde 106 voor beperkte toegangsmachtigingen. Voor machtigingen voor volledige toegang gebruikt u de waarde 236.

Voor aangepaste machtigingen gebruikt u de vorige tabel om de binaire waarde te krijgen die overeenkomt met de gepersonaliseerde machtigingen. Converteert de binaire waarde naar een decimale waarde en gebruik de decimaalwaarde voor de parameter _EndUserQuarantinePermissionsValue._

Zie [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>De parameter EndUserQuarantinePermissions gebruiken

Als u een quarantainetag wilt maken met _de parameter EndUserQuarantinePermissionsValue,_ gaat u als volgt te werk:

A. Sla een quarantainemachtigingsobject op in een variabele met de **cmdlet New-QuarantinePermissions.**

<p>

B. Gebruik de variabele als _de waarde EndUserQuarantinePermissions_ in de **opdracht New-QuarantineTag.**

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>Stap A: Een quarantainemachtigingsobject opslaan in een variabele

Gebruik de volgende syntaxis:

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

De standaardwaarde voor ongebruikte parameters is , dus u hoeft alleen de parameters te gebruiken waarop u de waarde `$false` wilt `$true` instellen.

In de volgende voorbeelden kunt u zien hoe u machtigingsobjecten maakt die overeenkomen met de vooraf ingestelde machtigingengroepen:

- **Geen toegang:**

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **Beperkte toegang:**

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **Volledige toegang:**

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

Als u de waarden wilt zien die u hebt ingesteld, moet u de variabelenaam uitvoeren als een opdracht (bijvoorbeeld de opdracht `$NoAccess` uitvoeren).

Stel voor aangepaste machtigingen de parameters _PermissionToRelease_ en _PermissionToRequestRelease_ niet in op `$true` . Stel de `$true` ene in en laat de andere als `$false` , of laat beide als `$false` .

U kunt ook een bestaande objectvariabele voor machtigingen wijzigen nadat u deze hebt gemaakt, maar voordat u deze gebruikt met de cmdlet **Set-QuarantinePermissions.**

Zie [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions)voor gedetailleerde syntaxis- en parametergegevens.

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>Stap B: De variabele gebruiken in de New-QuarantineTag opdracht

Nadat u het machtigingsobject in een variabele hebt gemaakt en opgeslagen, gebruikt u de variabele voor de _parameterwaarde EndUserQuarantinePermission_ in de volgende opdracht **New-QuarantineTag:**

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

In dit voorbeeld wordt een nieuwe quarantainetag met de naam LimitedAccess gemaakt met behulp van het machtigingsobject dat in de vorige stap is beschreven `$LimitedAccess` en gemaakt.

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

Zie [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>Stap 2: Een quarantainetag toewijzen aan ondersteunde functies

In _ondersteunde_ beveiligingsfuncties die berichten of bestanden in quarantaine plaatsen (automatisch of als een configureerbare actie), kunt u een quarantainelabel toewijzen aan de beschikbare quarantaineacties. Functies die berichten in quarantaine plaatsen en de beschikbaarheid van quarantainelabels worden beschreven in de volgende tabel:

<br>

****

|Functie|Worden quarantainelabels ondersteund?|Standaard quarantainelabels gebruikt|
|---|:---:|---|
|[Antispambeleid:](configure-your-spam-filter-policies.md) <ul><li>**Spam** (_SpamAction_)</li><li>**Spam met hoog vertrouwen** _(HighConfidenceSpamAction)_</li><li>**Phishing-e-mail** (_PhishSpamAction_)</li><li>**Phishing-e-mail** met hoog vertrouwen _(HighConfidencePhishAction)_</li><li>**Bulk-e-mail** (_BulkSpamAction_)</li></ul>|Ja|<ul><li>DefaultSpamTag (volledige toegang)</li><li>DefaultHighConfSpamTag (Volledige toegang)</li><li>DefaultPhishTag (volledige toegang)</li><li>DefaultHighConfPhishTag (Geen toegang)</li><li>DefaultBulkTag (Volledige toegang)</li></ul>
|Anti-phishingbeleid: <ul><li>[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</li><li>[Imitatiebeveiliging:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup> <ul><li>**Als e-mail wordt verzonden door een imiteerde gebruiker** (_TargetedUserProtectionAction_)</li><li>**Als e-mail wordt verzonden door een nagebootsd domein** (_TargetedDomainProtectionAction_)</li><li>**Postvakintelligentie** \> **Als e-mail wordt verzonden door een imiteerde gebruiker** (_MailboxIntelligenceProtectionAction_)</li></ul></li></ul></ul>|Nee|n/a|
|[Anti-malwarebeleid:](configure-anti-malware-policies.md)Alle gedetecteerde berichten worden altijd in quarantaine geplaatst.|Nee|n/a|
|[Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams](mdo-for-spo-odb-and-teams.md)|Nee|n/a|
|[Regels voor e-mailstroom](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transportregels genoemd) met de actie: Het bericht verzenden **naar de gehoste quarantaine** _(Quarantaine)._|Nee|n/a|
|

<sup>\*</sup> Instellingen voor imitatiebeveiliging zijn alleen beschikbaar in anti-phishingbeleid in Microsoft Defender voor Office 365.

Als u tevreden bent met de machtigingen voor eindgebruikers die worden geleverd door de standaard quarantainelabels, hoeft u niets te doen. Als u de mogelijkheden van eindgebruikers (beschikbare knoppen) wilt aanpassen in spammeldingen van eindgebruikers of in in quarantaine geplaatste berichtgegevens, kunt u een aangepaste quarantainetag toewijzen.

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>Quarantainelabels toewijzen in antispambeleid in het beveiligings- & compliancecentrum

Volledige instructies voor het maken en wijzigen van antispambeleid worden beschreven in [Antispambeleid](configure-your-spam-filter-policies.md)configureren in EOP.

1. Ga in het & Compliancecentrum naar **Beleid** voor bedreigingsbeheer \>  \> en selecteer vervolgens **Antispam.** Of open <https://protection.office.com/antispam> .

2. Zoek en selecteer een bestaand antispambeleid dat u wilt bewerken of maak een nieuw antispambeleid.

3. Vouw in de flyout beleidsdetails de sectie **Spam en bulkacties** uit.

4. Als u Quarantainebericht hebt geselecteerd voor de actie van  een beschikbare uitspraak voor het filteren van spam, is het vakJe quarantainebeleidtag toepassen beschikbaar om de quarantainetag voor dat vonnis te selecteren. 

   **Opmerking:** Wanneer u een nieuw beleid maakt, geeft een lege quarantainetagwaarde voor een vonnis voor spamfilters aan dat de standaard quarantainetag voor dat vonnis wordt gebruikt. Wanneer u het beleid later bewerkt, worden de lege waarden vervangen door de werkelijke standaardnamen van quarantainelabels zoals beschreven in de vorige tabel.

   ![Quarantainelabelselecties in een antispambeleid](../../media/quarantine-tags-in-anti-spam-policies.png)

5. Klik op **Opslaan** wanneer u gereed bent.

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>Quarantainelabels toewijzen in antispambeleid in PowerShell

Als u Liever PowerShell gebruikt om quarantainelabels toe te wijzen in antispambeleid, maakt u verbinding met Exchange Online PowerShell of Exchange Online Protection PowerShell en gebruikt u de volgende syntaxis:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Opmerkingen**:

- De standaardwaarde voor de parameter _HighConfidencePhishAction_ is Quarantaine, dus u hoeft de actie Quarantaine niet in te stellen voor phishingdetectie met veel vertrouwen in nieuwe antispambeleidsregels. Voor alle andere vonnissen voor spamfilters in nieuw of bestaand antispambeleid is de quarantainetag alleen van kracht als de actiewaarde Quarantaine is. Voer de volgende opdracht uit om de actiewaarden in bestaand antispambeleid te bekijken:

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  Zie [EOP-antispambeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)voor EOP voor informatie over de standaardactiewaarden en de aanbevolen actiewaarden voor Standaard en Strikt.

- Een vonnis voor spamfilters zonder een bijbehorende quarantainetagparameter betekent dat de [standaard quarantainetag](#step-2-assign-a-quarantine-tag-to-supported-features) voor dat vonnis wordt gebruikt.

  U hoeft alleen een standaard quarantainetag te vervangen door een aangepaste quarantainetag als u de standaardmogelijkheden van eindgebruikers voor in quarantaine geplaatste berichten wilt wijzigen.

- Voor een nieuw antispambeleid in PowerShell is een spamfilterbeleid (instellingen) vereist met de cmdlet **New-HostedContentFilterPolicy** en een nieuwe spamfilterregel (ontvangersfilters) met de cmdlet **New-HostedContentFilterRule.** Zie [PowerShell gebruiken om antispambeleid te maken](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)voor instructies.

In dit voorbeeld wordt een nieuw spamfilterbeleid met de naam Onderzoeksafdeling gemaakt met de volgende instellingen:

- De actie voor alle vonnissen voor spamfilters is ingesteld op Quarantaine.
- De aangepaste quarantainetag met de naam  NoAccess die Geen toegangsmachtigingen  toewijst, vervangt standaard quarantainelabels die standaard geen toegangsmachtigingen toewijzen.

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

Zie [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

Dit voorbeeld wijzigt het bestaande spamfilterbeleid met de naam Human Resources. De actie voor de quarantaine van spam is ingesteld op Quarantaine en de aangepaste quarantainetag noAccess wordt toegewezen.

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

Zie [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>Instellingen voor globale quarantainemeldingen configureren in & Beveiligingscentrum

Met de algemene instellingen voor quarantainelabels kunt u de spammeldingen van eindgebruikers aanpassen die worden verzonden naar geadresseerden van berichten die in quarantaine zijn geplaatst. Zie [Spammeldingen](use-spam-notifications-to-release-and-report-quarantined-messages.md)voor eindgebruikers voor meer informatie over deze meldingen.

1. Ga in het & Compliancecentrum naar **Bedreigingsbeleid** \>  en selecteer vervolgens **Quarantainelabels.**

2. Selecteer globale instellingen op **de** pagina **Quarantainelabels.**

3. Configureer **enkele** of alle volgende instellingen in het flyout Quarantainemeldingsinstellingen dat wordt geopend:

   - **Mijn bedrijfslogo gebruiken:** Selecteer deze optie om het standaard Microsoft-logo te vervangen dat boven aan spammeldingen van eindgebruikers wordt gebruikt. Voordat u dit doet, moet u de instructies volgen in [Het Microsoft 365-thema](../../admin/setup/customize-your-organization-theme.md) aanpassen voor uw organisatie om uw aangepaste logo te uploaden.

     In de volgende schermafbeelding ziet u een aangepast logo in een spammelding voor eindgebruikers:

     ![Een aangepast logo in een spammelding voor eindgebruikers](../../media/quarantine-tags-esn-customization-logo.png)

   - **Taal kiezen:** spammeldingen van eindgebruikers zijn al gelokaliseerd op basis van de taalinstellingen van de geadresseerde. U kunt aangepaste tekst opgeven in verschillende talen voor de **waarden Weergavenaam** en **Vrijwaring.**

     Selecteer ten minste één taal in het vak eerste taal en klik vervolgens op **Toevoegen.** U kunt meerdere talen selecteren door na elke taal op **Toevoegen** te klikken. In een sectietaalvak ziet u alle talen die u hebt geselecteerd:

     ![Geselecteerde talen in het tweede taalvak in de algemene instellingen voor quarantainemeldingen van quarantainelabels](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **Weergavenaam:** Pas de weergavenaam van de afzender aan die wordt gebruikt in spammeldingen van eindgebruikers.

     Voor elke taal die u hebt toegevoegd, selecteert u de taal in het vak tweede taal (klik niet op de X) en typt u de tekstwaarde die u wilt gebruiken in het vak **Weergavenaam.**

     In de volgende schermafbeelding ziet u de aangepaste weergavenaam in een spammelding voor eindgebruikers:

     ![Een aangepaste weergavenaam voor afzenders in een spammelding voor eindgebruikers](../../media/quarantine-tags-esn-customization-display-name.png)

   - **Vrijwaring:** Voeg een aangepaste vrijwaring toe aan de onderkant van spammeldingen van eindgebruikers. De gelokaliseerde tekst, **Een vrijwaring van uw organisatie:** wordt altijd eerst opgenomen, gevolgd door de tekst die u opgeeft.

     Voor elke taal die u hebt toegevoegd, selecteert u de taal in het vak tweede taal (klik niet op de X) en typt u de tekstwaarde die u wilt gebruiken in het vak **Vrijwaring.**

     In de volgende schermafbeelding ziet u de aangepaste vrijwaring in een spammelding voor eindgebruikers:

     ![Een aangepaste vrijwaring onder aan een spammelding voor eindgebruikers](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>Quarantainelabels weergeven in het beveiligings- & compliancecentrum

1. Ga in het & Compliancecentrum naar **Bedreigingsbeleid** \>  en selecteer vervolgens **Quarantainelabels.**

- Als u de instellingen van ingebouwde of aangepaste quarantainelabels wilt weergeven, selecteert u de quarantainetag in de lijst (schakel het selectievakje niet in).

- Als u de algemene instellingen wilt weergeven, **selecteert** u Algemene instellingen

### <a name="view-quarantine-tags-in-powershell"></a>Quarantainelabels weergeven in PowerShell

Als u Liever PowerShell gebruikt om quarantainelabels weer te geven, gaat u als volgt te werk:

- Voer de volgende opdracht uit als u een overzichtslijst met alle ingebouwde of aangepaste tags wilt weergeven:

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- Als u de instellingen van ingebouwde of aangepaste quarantainelabels wilt weergeven, vervangt u de naam van de quarantainetag en voer u \<TagName\> de volgende opdracht uit:

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- Voer de volgende opdracht uit om de algemene instellingen weer te geven:

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

Zie [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>Quarantainelabels verwijderen in het beveiligings- & compliancecentrum

**Opmerkingen**:

- U kunt ingebouwde quarantainelabels niet verwijderen.

- Controleer voordat u een aangepaste quarantainetag verwijdert of deze niet wordt gebruikt. Voer bijvoorbeeld de volgende opdracht uit in PowerShell:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  Als de quarantainetag wordt gebruikt, [vervangt u de toegewezen quarantainetag](#step-2-assign-a-quarantine-tag-to-supported-features) voordat u deze verwijdert.

1. Ga in het & Compliancecentrum naar **Bedreigingsbeleid** \>  en selecteer vervolgens **Quarantainelabels.**

2. Selecteer op **de pagina Quarantainelabels** de aangepaste quarantainetag die u wilt verwijderen en klik op **Tag verwijderen.**

3. Klik **op Tag verwijderen** in het bevestigingsdialoogvenster dat wordt weergegeven.

### <a name="remove-quarantine-tags-in-powershell"></a>Quarantainelabels verwijderen in PowerShell

Als u Liever PowerShell gebruikt om een aangepaste quarantainetag te verwijderen, vervangt u de naam van de quarantainetag en voer u \<TagName\> de volgende opdracht uit:

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

Zie [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="quarantine-tag-permission-details"></a>Machtigingsgegevens voor quarantainelabels

In de volgende secties worden de effecten beschreven van vooraf ingestelde machtigingsgroepen en afzonderlijke machtigingen in de details van in quarantaine geplaatste berichten en in spammeldingen van eindgebruikers.

### <a name="preset-permissions-groups"></a>Vooraf ingestelde machtigingengroepen

De afzonderlijke machtigingen die zijn opgenomen in vooraf ingestelde machtigingsgroepen, worden weergegeven in de tabel aan het begin van dit artikel.

#### <a name="no-access"></a>Geen toegang

Als de quarantainetag  geen toegangsmachtigingen (geen machtigingen) toewijst, krijgen gebruikers nog steeds enkele basislijnfuncties:

- **Berichtdetails in quarantaine:** **de knop Berichtkop** weergeven is altijd beschikbaar.

  ![Beschikbare knoppen in de details van het in quarantaine geplaatste bericht als de gebruiker geen toegangsmachtigingen krijgt met de quarantainetag](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **Spammeldingen van eindgebruikers:** **de** knop Controleren waarmee de gebruiker in quarantaine naar het bericht gaat, is altijd beschikbaar.

  ![Beschikbare knoppen in de spammelding voor eindgebruikers als de gebruiker geen toegangsmachtigingen krijgt met de quarantainetag](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>Beperkte toegang

Als met de quarantainetag de machtiging Beperkte **toegang** wordt toegewezen, krijgen gebruikers de volgende mogelijkheden:

- **Details van berichten in quarantaine**: De volgende knoppen zijn beschikbaar:
  - **Release aanvragen**
  - **Berichtkop weergeven**
  - **Voorbeeld van bericht**
  - **Afzender blokkeren**
  - **Uit quarantaine verwijderen**

  ![Beschikbare knoppen in de details van het in quarantaine geplaatste bericht als de gebruiker met de quarantainetag beperkte toegangsmachtigingen krijgt](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **Spammeldingen voor eindgebruikers:** De volgende knoppen zijn beschikbaar:
  - **Afzender blokkeren**
  - **Controle**

  ![Beschikbare knoppen in de spammelding voor eindgebruikers als de quarantainetag de gebruiker beperkte toegangsmachtigingen geeft](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>Volledige toegang

Als de quarantainetag  de machtiging volledige toegang (alle beschikbare machtigingen) toewijst, krijgen gebruikers de volgende mogelijkheden:

- **Details van berichten in quarantaine**: De volgende knoppen zijn beschikbaar:
  - **Releasebericht**
  - **Berichtkop weergeven**
  - **Voorbeeld van bericht**
  - **Afzender blokkeren**
  - **Afzender toestaan**
  - **Uit quarantaine verwijderen**

  ![Beschikbare knoppen in de details van het in quarantaine geplaatste bericht als de gebruiker met de quarantainetag volledige toegangsmachtigingen krijgt](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **Spammeldingen voor eindgebruikers:** De volgende knoppen zijn beschikbaar:
  - **Afzender blokkeren**
  - **Release**
  - **Controle**

  ![Beschikbare knoppen in de spammelding voor eindgebruikers als de quarantainetag de gebruiker volledige toegangsmachtigingen geeft](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>Afzonderlijke machtigingen

> [!NOTE]
> Vergeet niet dat gebruikers altijd de knoppen krijgen die worden beschreven in [de sectie Geen toegang.](#no-access) Deze knoppen zijn niet opgenomen in de afzonderlijke machtigingsbeschrijvingen.

#### <a name="allow-sender-permission"></a>Afzendermachtiging toestaan

Met **de machtiging Afzender** toestaan _(PermissionToAllowSender)_ wordt de toegang tot de knop besturingselementen waarmee gebruikers de afzender van het in quarantaine geplaatste bericht gemakkelijk kunnen toevoegen aan de lijst met Safe afzenders.

- **Details van berichten in quarantaine:**
  - **Afzendermachtiging** toestaan ingeschakeld: **de knop Afzender toestaan** is beschikbaar.
  - **Afzendermachtiging** toestaan uitgeschakeld: **de knop Afzender toestaan** is niet beschikbaar.

- **Spammeldingen van eindgebruikers:** Geen effect.

Zie Voorkomen dat vertrouwde [afzenders](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) worden geblokkeerd en Gebruik Exchange Online PowerShell om de [safelistverzameling](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)in een postvak te configureren voor meer informatie over de lijst met Safe-afzenders.

#### <a name="block-sender-permission"></a>Afzendermachtiging blokkeren

De **machtiging Afzender blokkeren** _(PermissionToBlockSender)_ bepaalt de toegang tot de knop waarmee gebruikers de afzender van het in quarantaine geplaatste bericht gemakkelijk kunnen toevoegen aan hun lijst met geblokkeerde afzenders.

- **Details van berichten in quarantaine:**
  - **Afzendermachtiging** blokkeren ingeschakeld: de **knop Afzender blokkeren** is beschikbaar.
  - **Afzendermachtiging** blokkeren uitgeschakeld: de **knop Afzender blokkeren** is niet beschikbaar.

- **Spammeldingen voor eindgebruikers:**
  - **Afzendermachtiging** blokkeren uitgeschakeld: de **knop Afzender blokkeren** is niet beschikbaar.
  - **Afzendermachtiging** blokkeren ingeschakeld: de **knop Afzender blokkeren** is beschikbaar.

Zie Berichten van iemand blokkeren en [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) Gebruik Exchange Online PowerShell om de safelistverzameling in een postvak te configureren voor meer informatie over de lijst geblokkeerde [afzenders.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)

#### <a name="delete-permission"></a>Machtiging voor verwijderen

Met **de machtiging** Verwijderen _(PermissionToDelete)_ wordt de mogelijkheid van gebruikers om hun berichten (berichten waar de gebruiker een geadresseerde is) uit quarantaine te verwijderen.

- **Details van berichten in quarantaine:**
  - **Machtiging** verwijderen ingeschakeld: de **knop Verwijderen uit quarantaine** is beschikbaar.
  - **Machtiging** verwijderen uitgeschakeld: de **knop Verwijderen uit quarantaine** is niet beschikbaar.

- **Spammeldingen van eindgebruikers:** Geen effect.

#### <a name="preview-permission"></a>Voorbeeldmachtiging

De **machtiging Voorbeeld** (_PermissionToPreview_) bepaalt de mogelijkheid voor gebruikers om een voorbeeld van hun berichten in quarantaine te bekijken.

- **Details van berichten in quarantaine:**
  - **Voorbeeldmachtiging** ingeschakeld: de **knop Voorbeeldbericht** is beschikbaar.
  - **Voorbeeldmachtiging** uitgeschakeld: de **knop Voorbeeldbericht** is niet beschikbaar.

- **Spammeldingen van eindgebruikers:** Geen effect.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Toestaan dat geadresseerden een bericht vrijgeven van quarantainemachtigingen

Met **De machtiging** Toestaan dat geadresseerden een bericht vrijgeven van quarantainemachtigingen _(PermissionToRelease)_ bepaalt de mogelijkheid van gebruikers om hun in quarantaine geplaatste berichten rechtstreeks en zonder de goedkeuring van een beheerder vrij te geven.

- **Details van berichten in quarantaine:**
  - Machtiging ingeschakeld: de **knop Bericht vrijgeven** is beschikbaar.
  - Machtiging uitgeschakeld: de **knop Bericht vrijgeven** is niet beschikbaar.

- **Spammeldingen voor eindgebruikers:**
  - Machtiging ingeschakeld: de **knop Release** is beschikbaar.
  - Machtiging uitgeschakeld: de **knop Release** is niet beschikbaar.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Ontvangers toestaan om een bericht te vragen om uit quarantainemachtigingen te worden vrijgegeven

Met **De machtiging** Geadresseerden toestaan om een bericht uit quarantainemachtigingen te verwijderen  _(PermissionToRequestRelease)_ bepaalt de mogelijkheid van gebruikers om de release van hun in quarantaine geplaatste berichten aan te vragen. Het bericht wordt alleen uitgebracht nadat een beheerder de aanvraag heeft goedgekeurd.

- **Details van berichten in quarantaine:**
  - Machtiging ingeschakeld: de **knop Release aanvragen** is beschikbaar.
  - Machtiging uitgeschakeld: de **knop Release** aanvragen is niet beschikbaar.

- **Spammeldingen van eindgebruikers:** de **knop Release** is niet beschikbaar.