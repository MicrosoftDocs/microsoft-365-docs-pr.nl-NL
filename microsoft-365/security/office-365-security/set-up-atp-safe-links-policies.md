---
title: Beleidsregels voor veilige koppelingen instellen in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie lezen over het weergeven, maken, wijzigen en verwijderen van beleid voor veilige koppelingen en algemene instellingen voor veilige koppelingen in Office 365 Advanced Threat Protection (ATP).
ms.openlocfilehash: 58088955a6909238c1fe5202688e0b8d1ab8e6c6
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327223"
---
# <a name="set-up-safe-links-policies-in-office-365-atp"></a>Beleidsregels voor veilige koppelingen instellen in Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Office 365 Advanced Threat Protection](office-365-atp.md) hebben. Als u een thuisgebruiker bent die op zoek bent naar informatie over Safelinks in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Veilige koppelingen is een functie in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) voor het scannen van inkomende e-mailberichten in de e-mail stroom, en de tijd van de verificatie van url's en koppelingen in e-mailberichten en op andere locaties. Zie voor meer informatie [veilige koppelingen in Office 365 ATP](atp-safe-links.md).

Er is geen ingebouwd of standaardbeleid voor veilige koppelingen. Als u op zoek bent naar het scannen van Url's, moet u een of meer beleidsregels voor veilige koppelingen maken, zoals wordt beschreven in dit artikel.

U kunt beleidsregels voor veilige koppelingen configureren in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Office 365.

De basiselementen van een beleid voor veilige koppelingen zijn:

- **Het beleid voor veilige**koppelingen: Schakel beveiliging van veilige koppelingen in, schakel de mogelijkheid om in realtime url's in te schakelen en geef aan of u wilt wachten tot de realtime-controle is voltooid voordat u het bericht bezorgt, de scanfunctie voor interne berichten opgeeft en opgeven of gebruikers de muisklik op de URL moeten volgen en opgeven of gebruikers op Trough kunnen klikken voor de oorspronkelijke URL.
- **De regel voor veilige koppelingen**: Hiermee geeft u de prioriteit op voor de filters voor de prioriteit en de geadresseerden (waarvoor het beleid van toepassing is).

Het verschil tussen deze twee elementen is niet duidelijk wanneer u beleidsregels voor veilige koppelingen beheert in het beveiligings & nalevings centrum:

- Wanneer u een beleid voor veilige koppelingen maakt, maakt u eigenlijk een regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen tegelijk met dezelfde naam.
- Wanneer u een beleid voor veilige koppelingen wijzigt, worden de instellingen voor de naam, de prioriteit, ingeschakeld of uitgeschakeld en de filters voor geadresseerden gewijzigd in de regel voor veilige koppelingen. Alle andere instellingen wijzigen het bijbehorende beleid voor veilige koppelingen.
- Wanneer u een beleid voor veilige koppelingen verwijdert, worden de regels voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie voor meer informatie het artikel [Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken voor het configureren van beleidsregels voor veilige koppelingen](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) verderop in dit artikel.

> [!NOTE]
> U configureert de algemene instellingen voor beveiliging van veilige koppelingen **buiten** het beleid voor veilige koppelingen. Zie [algemene instellingen configureren voor veilige koppelingen in Office 365 ATP](configure-global-settings-for-safe-links.md)voor instructies.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u direct naar de pagina voor **veilige koppelingen voor ATP** wilt gaan, gebruikt u <https://protection.office.com/safelinksv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- Voor het weergeven, maken, wijzigen en verwijderen van beleid voor veilige koppelingen, moet u lid zijn van een van de volgende groepen rollen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
  - **Organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Zie [beleidsinstellingen voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)voor de aanbevolen instellingen voor beleidsregels voor veilige koppelingen.

- Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.

- [Nieuwe functies worden continu toegevoegd aan ATP](office-365-atp.md#new-features-in-office-365-atp). Wanneer nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleid voor veilige koppelingen aanpassen.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige koppelingen te maken

Als u een aangepast beleid voor veilige koppelingen maakt in de beveiligings & nalevings centrum, wordt de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen tegelijk gemaakt met dezelfde naam voor beide.

1. Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen**voor het beleid voor bedreigings beheer.

2. Klik op de pagina **veilige koppelingen** op **maken**.

3. De wizard **beleid voor nieuwe beleidsregels** wordt geopend. Configureer de volgende instellingen op de pagina **naam van uw beleid** :

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Wanneer u klaar bent, klikt u op **volgende**.

4. Configureer de volgende instellingen op de pagina **instellingen** die wordt weergegeven:

   - **Selecteer de actie voor onbekende, mogelijk schadelijke url's in berichten**: Selecteer **aan**.

   - **Selecteer de actie voor onbekende mogelijk schadelijke url's in berichten**: Selecteer **aan** of laat de standaardwaarde **uit** geselecteerd.

   - Het **scannen van realtime-Url's toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden**: Selecteer deze instelling om de realtime scan van koppelingen in e-mailberichten in te schakelen.

   - **Wacht totdat het scannen van url's is voltooid voordat u het bericht bezorgt**: Selecteer deze instelling om te wachten tot de realtime-URL wordt gescand voordat u het bericht aflevert.

   - **Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden**: Selecteer deze instelling om het beleid voor veilige koppelingen toe te passen op berichten tussen interne afzenders en interne geadresseerden.

   - **Gebruikers niet op klikken volgen**: laat deze instelling uitgeschakeld om de gebruiker te laten klikken op url's in e-mailberichten.

   - **Gebruikers niet toestaan door de oorspronkelijke URL**te klikken: Selecteer deze instelling om te voorkomen dat gebruikers op de oorspronkelijke URL van [waarschuwings pagina's](atp-safe-links.md#warning-pages-from-safe-links)klikken.

   - **Schrijf niet de volgende url's**opnieuw op: Hiermee kan de opgegeven url's worden geopend die anders worden geblokkeerd door veilige koppelingen.

     Typ in het vak de gewenste URL of waarde en klik vervolgens op ![Knoppictogram toevoegen](../../media/ITPro-EAC-AddIcon.png).

     Als u een bestaande vermelding wilt verwijderen, selecteert u deze en klikt u op ![Pictogramknop verwijderen](../../media/ITPro-EAC-DeleteIcon.png).

     Zie de [invoer syntaxis voor de lijst ' de volgende url's niet herschrijven ' voor de](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)invoer syntaxis.

   Zie [instellingen voor veilige koppelingen voor e-mailberichten](atp-safe-links.md#safe-links-settings-for-email-messages) en [instellingen voor veilige koppelingen voor Microsoft teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams)voor meer informatie over deze instellingen.

   Zie [beleidsinstellingen voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)voor de aanbevolen waarden voor de standaard-en strikte beleidsinstellingen.

   Wanneer u klaar bent, klikt u op **volgende**.

5. Op de pagina **toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden waarop het beleid van toepassing is.

   U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

   Klik op **een voorwaarde toevoegen**. Selecteer een voorwaarde in de vervolgkeuzelijst die wordt weergegeven **als**:

   - **De ontvanger is**: geeft een of meer postvakken, e-mail gebruikers of e-mail contactpersonen in uw organisatie op.
   - **De ontvanger is lid van**: Hiermee geeft u een of meer groepen op in uw organisatie.
   - **Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.

   Wanneer u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzelijst weergegeven met een **van deze** vakken.

   - Klik in het vak en blader door de lijst met waarden die u wilt selecteren.
   - Klik in het vak en begin te typen om de lijst te filteren en een waarde te selecteren.
   - Als u extra waarden wilt toevoegen, klikt u op een leeg gebied in het vak.
   - Als u afzonderlijke vermeldingen wilt verwijderen **, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de waarde.
   - Als u de hele voorwaarde wilt verwijderen **, klikt u op** ![ pictogram verwijderen ](../../media/scc-remove-icon.png) in de voorwaarde.

   Als u een extra voorwaarde wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een resterende waarde onder **toegepast als**.

   Als u uitzonderingen wilt toevoegen, klikt u op **een voorwaarde toevoegen** en selecteert u een uitzondering onder **behalve als**. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Wanneer u klaar bent, klikt u op **volgende**.

6. Controleer de instellingen op de pagina **uw instellingen bekijken** die wordt weergegeven. U kunt op de verschillende instellingen klikken om de **bewerking** te wijzigen.

   Wanneer u klaar bent, klikt u op **Voltooien**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Het Beveiligingscentrum beveiligings & gebruiken om beleidsregels voor veilige koppelingen weer te geven

1. Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen**voor het beleid voor bedreigings beheer.

2. Selecteer een beleid in de lijst op de pagina **veilige koppelingen** en klik erop (niet het selectievakje inschakelen).

   De beleidsdetails worden in een uitgelichte vlucht weergegeven

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige koppelingen te wijzigen

1. Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen**voor het beleid voor bedreigings beheer.

2. Selecteer een beleid in de lijst op de pagina **veilige koppelingen** en klik erop (niet het selectievakje inschakelen).

3. Klik in de beleidsdetails die worden weergegeven, op **beleid bewerken**.

Welke van de beschikbare instellingen in de vlucht die wordt weergegeven, zijn identiek aan de instellingen die worden beschreven in de sectie [het beveiligings & gebruiken om de beleidsregels voor veilige koppelingen te maken](#use-the-security--compliance-center-to-create-safe-links-policies) .

Zie de volgende secties als u een beleid wilt in-of uitschakelen of de prioriteitsvolgorde voor beleidsregels wilt instellen.

### <a name="enable-or-disable-safe-links-policies"></a>Beleidsregels voor veilige koppelingen in-of uitschakelen

1. Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen**voor het beleid voor bedreigings beheer.

2. Let op de waarde in de kolom **status** :

   - Verplaats te wisselknop naar links om het beleid uit te schakelen: ![Beleid uitschakelen](../../media/scc-toggle-off.png).

   - Verplaats te wisselknop naar rechts om het beleid in te schakelen: ![Beleid inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

### <a name="set-the-priority-of-safe-links-policies"></a>De prioriteit voor beleidsregels voor veilige koppelingen instellen

Beleidsregels voor veilige koppelingen krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwe policies zijn een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Beleidsregels voor veilige koppelingen worden weergegeven in de volgorde waarin ze worden verwerkt ( **het eerste** beleid heeft de waarde 0).

**Opmerking**: in het beveiligings & nalevings centrum kunt u de prioriteit van het beleid voor veilige koppelingen alleen wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit negeren wanneer u de regel voor veilige koppelingen maakt (die van invloed kunnen zijn op de prioriteit van bestaande regels).

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit**snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen**voor het beleid voor bedreigings beheer.

2. Selecteer een beleid in de lijst op de pagina **veilige koppelingen** en klik erop (niet het selectievakje inschakelen).

3. Klik in het venster Details van het beleid dat wordt weergegeven op de knop beschikbare prioriteit:

   - Voor het beleid voor veilige koppelingen met de **prioriteits** waarde **0** is slechts de knop **prioriteit verlagen** beschikbaar.

   - Het beleid voor veilige koppelingen met de laagste **prioriteits** waarde (bijvoorbeeld **3**) is alleen beschikbaar voor de knop **prioriteit verhogen** .

   - Als u een beleidsregels voor veilige koppelingen hebt, kunt u beleidsregels gebruiken tussen de waarden voor de hoogste en laagste prioriteit, en de knoppen prioriteit **verhogen** en **prioriteit verlagen** .

4. Klik op **prioriteit verhogen** of **prioriteit verkleinen** om de **prioriteits** waarde te wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige koppelingen te verwijderen

1. Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen**voor het beleid voor bedreigings beheer.

2. Selecteer een beleid in de lijst op de pagina **veilige koppelingen** en klik erop (niet het selectievakje inschakelen).

3. Ga naar de details van het beleid dat wordt weergegeven, klik op **beleid verwijderen**en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Beleidsregels voor veilige koppelingen met Exchange Online PowerShell of zelfstandige EOP PowerShell configureren

Zoals hierboven beschreven, bestaat een beleid voor veilige koppelingen van een beleid voor veilige koppelingen en een regel voor veilige koppelingen.

In PowerShell is het verschil tussen beleid voor veilige koppelingen en regels voor veilige koppelingen duidelijk. U beheert beleidsregels voor veilige koppelingen met behulp van de ** \* SafeLinksPolicy-** cmdlets en u beheert regels voor veilige koppelingen met behulp van de cmdlets voor ** \* SafeLinksRule** .

- In PowerShell maakt u eerst het beleid voor veilige koppelingen en vervolgens maakt u de regel voor veilige koppelingen waarmee het beleid wordt aangegeven waarop de regel van toepassing is.
- In PowerShell wijzigt u de instellingen in het beleid voor veilige koppelingen en de regel voor veilige koppelingen afzonderlijk.
- Wanneer u een beleid voor veilige koppelingen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-safe-links-policies"></a>PowerShell gebruiken om beleid voor veilige koppelingen te maken

Het maken van een beleid voor veilige koppelingen in PowerShell is een procedure die bestaat uit twee stappen:

1. Maak het beleid voor veilige koppelingen.
2. Maak de regel voor veilige koppelingen die het beleid voor veilige koppelingen opgeeft waarop de regel van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe regel voor veilige koppelingen maken en hieraan een bestaand, niet-gekoppeld beleid voor veilige koppelingen toewijzen. Een regel voor veilige koppelingen kan niet worden gekoppeld aan meer dan één beleid voor veilige koppelingen.

- U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige koppelingen in PowerShell die niet beschikbaar zijn in het beveiligings & nalevings centrum voordat u het beleid hebt gemaakt:

  - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld_ `$false` in de **nieuwe SafeLinksRule-** cmdlet).
  - De prioriteit van het beleid instellen voor het maken_Priority_ van de _\<Number\>_ **nieuwe SafeLinksRule-** cmdlet (prioriteit).

- Een nieuw beleid voor veilige koppelingen dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een regel voor veilige koppelingen toewijst.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken

Als u een beleid voor veilige koppelingen wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**Opmerkingen**:

- Zie de [invoer syntaxis voor de lijst ' de volgende url's niet herschrijven '](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)voor meer informatie over de syntaxis van de _DoNotRewriteUrls_ -parameter.

- Zie het gedeelte [beleidsregels voor veilige koppelingen in PowerShell gebruiken](#use-powershell-to-modify-safe-links-policies) voor het wijzigen van de beleidsregels voor veilige koppelingen in dit artikel voor meer informatie over het gebruik van de parameter _DoNotRewriteUrls_ wanneer u bestaande beleidsregels voor veilige koppelingen wijzigt met behulp van de cmdlet **set-SafeLinksPolicy** .

In dit voorbeeld wordt een beleid voor veilige koppelingen gemaakt met de naam contoso all en de volgende waarden:

- Schakel URL Scanning in en herschrijf u in e-mailberichten.
- Het scannen van URL'S in teams inschakelen (alleen op voorbeeld).
- Schakel realtime scanning van geklikt url's in, waaronder geklikt koppelingen die naar bestanden verwijzen.
- Wacht totdat URL-Scan is voltooid voordat u het bericht aflevert.
- Schakel URL Scanning in en herschrijf voor interne berichten.
- Gebruikers klikken met betrekking tot beveiliging van veilige koppelingen bijhouden (de parameter _DoNotTrackUserClicks_ wordt niet gebruikt en de standaardwaarde is $False, wat betekent dat de gebruiker klikt op bijhouden).
- Gebruikers kunnen niet naar de oorspronkelijke URL klikken.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Zie [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)voor gedetailleerde syntaxis-en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Stap 2: PowerShell gebruiken om een regel voor veilige koppelingen te maken

Gebruik de volgende syntaxis om een regel voor veilige koppelingen te maken:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In dit voorbeeld wordt een regel voor veilige koppelingen gemaakt met de naam contoso all met de volgende voorwaarden:

- De regel is gekoppeld aan het beleid voor veilige koppelingen met de naam contoso all.
- De regel geldt voor alle geadresseerden in het contoso.com-domein.
- Aangezien we de _prioriteits_ parameter niet gebruiken, wordt de standaardprioriteit gebruikt.
- De regel is ingeschakeld (de _ingeschakelde_ parameter wordt niet gebruikt en de standaardwaarde is `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Zie [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-view-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen weer te geven

Als u bestaande beleidsregels voor veilige koppelingen wilt bekijken, gebruikt u de volgende syntaxis:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst weergegeven met alle beleidsregels voor veilige koppelingen.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor het beleid voor veilige koppelingen met de naam contoso-leidinggevenden.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Zie [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-view-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen weer te geven

Als u bestaande regels voor veilige koppelingen wilt bekijken, gebruikt u de volgende syntaxis:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst weergegeven met alle regels voor veilige koppelingen.

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor de regel voor veilige koppelingen met de naam contoso-leidinggevenden.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Zie [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-safe-links-policies"></a>Beleidsregels voor veilige koppelingen wijzigen met PowerShell

U kunt de naam van een beleid voor veilige koppelingen in PowerShell niet wijzigen (de cmdlet **set-SafeLinksPolicy** heeft geen _naam_ parameter). Wanneer u de naam van een beleid voor veilige koppelingen in het beveiligings & nalevings centrum wijzigt, kunt u alleen de naam van de _regel_voor veilige koppelingen wijzigen.

De enige extra overweging voor het wijzigen van het beleid voor veilige koppelingen in PowerShell is de beschikbare syntaxis voor de parameter _DoNotRewriteUrls_ (de [lijst ' de volgende url's niet herschrijven '](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):

- Als u waarden wilt toevoegen waarmee bestaande vermeldingen worden vervangen, gebruikt u de volgende syntaxis: `"Entry1","Entry2,..."EntryN"` .
- Gebruik de volgende syntaxis om waarden toe te voegen of te verwijderen zonder dat dit invloed heeft op andere bestaande vermeldingen: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

U kunt ook dezelfde instellingen gebruiken als u een beleid voor veilige koppelingen maakt zoals wordt beschreven in de sectie [stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken](#step-1-use-powershell-to-create-a-safe-links-policy) eerder in dit artikel.

Als u een beleid voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Zie [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen te wijzigen

De enige instelling die niet beschikbaar is wanneer u een regel voor veilige koppelingen in PowerShell wijzigt, is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor veilige koppelingen wilt in-of uitschakelen.

Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals wordt beschreven in de sectie [stap 2: PowerShell gebruiken om een sectie voor veilige koppelingen te maken](#step-2-use-powershell-to-create-a-safe-links-rule) eerder in dit artikel.

Als u een regel voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Zie [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen in of uit te schakelen

Door een regel voor veilige koppelingen in of uit te schakelen in PowerShell wordt het volledige beleid voor veilige koppelingen en het beleid voor veilige koppelingen uitgeschakeld.

Gebruik de volgende syntaxis om een regel voor veilige koppelingen in PowerShell in of uit te schakelen:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de regel voor veilige koppelingen genaamd marketing afdeling uitgeschakeld.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Zie [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) en [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>PowerShell gebruiken voor het instellen van de prioriteit van regels voor veilige koppelingen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit wilt instellen van een regel voor veilige koppelingen in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

**Opmerking**: als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-SafeLinksRule** .

Zie [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-remove-safe-links-policies"></a>Beleidsregels voor veilige koppelingen verwijderen met PowerShell

Wanneer u met PowerShell een beleid voor veilige koppelingen verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet verwijderd.

Als u een beleid voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het beleid voor veilige koppelingen met de naam marketing afdeling verwijderd.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Zie [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-remove-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen te verwijderen

Wanneer u PowerShell gebruikt om een regel voor veilige koppelingen te verwijderen, wordt het bijbehorende beleid voor veilige koppelingen niet verwijderd.

Als u een regel voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de regel voor veilige koppelingen met de naam marketing afdeling verwijderd.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Zie [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)voor gedetailleerde syntaxis-en parameterinformatie.

Kijk op de beschikbare rapporten van de geavanceerde Bedreigingsbeveiliging als u wilt controleren of veilige koppelingen berichten scannen. Voor meer informatie raadpleegt u [rapporten weergeven voor Office 365 ATP](view-reports-for-atp.md) en [gebruikt u de Verkenner in het beveiligings & nalevings centrum](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Voer een van de volgende stappen uit om te controleren of u het beleid voor veilige koppelingen hebt gemaakt, gewijzigd of verwijderd:

- Ga in het beveiligings & nalevings centrum naar **Threat management** \> **Policy** \> **veilige koppelingen**voor het beleid voor bedreigings beheer. Controleer de lijst met beleidsregels, de **status** waarden en de waarden van de **prioriteit** . Als u meer informatie wilt bekijken, selecteert u het beleid in de lijst en bekijkt u de details in de vlucht.

- In Exchange Online PowerShell of Exchange Online Protection PowerShell vervangt u \<Name\> de naam van het beleid of de regel door de volgende opdracht uit te voeren en de instellingen te controleren:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
