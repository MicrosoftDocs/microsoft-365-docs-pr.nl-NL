---
title: Beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het weergeven, maken, wijzigen en verwijderen van beleidsregels voor veilige koppelingen en globale instellingen voor veilige koppelingen in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c8b2cb8b57dcf630b3e07ac387e96ab099ca7403
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058525"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](defender-for-office-365.md) hebben. Als u een thuisgebruiker bent die informatie zoekt over Safelinks in Outlook, bekijkt u [Geavanceerde Outlook.com beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Veilige koppelingen is een functie in Microsoft Defender voor [Office 365](defender-for-office-365.md) waarmee url's worden gescand van binnenkomende e-mailberichten in de e-mailstroom en het tijdstip van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties. Zie Veilige koppelingen [in Microsoft Defender voor Office 365](safe-links.md)voor meer informatie.

Er is geen ingebouwd of standaardbeleid voor veilige koppelingen. Als u veilige koppelingen wilt laten scannen op URL's, moet u een of meer beleidsregels voor veilige koppelingen maken, zoals wordt beschreven in dit artikel.

> [!NOTE]
> U configureert de algemene instellingen voor beveiliging van veilige koppelingen **buiten het** beleid voor veilige koppelingen. Zie Algemene instellingen [configureren voor veilige koppelingen in Microsoft Defender voor Office 365](configure-global-settings-for-safe-links.md)voor instructies.

U kunt beleidsregels voor veilige koppelingen configureren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).

De basiselementen van een beleid voor veilige koppelingen zijn:

- Het beleid voor veilige **koppelingen:** Schakel beveiliging voor veilige koppelingen in, schakel realtime URL-scannen in, geef op of u moet wachten totdat het scannen in realtime moet worden voltooid voordat het bericht wordt verzonden, scan naar interne berichten in te stellen, op te geven of gebruikersklikken op URL's moeten bijhouden en of gebruikers mogen klikken op de oorspronkelijke URL.
- **De regel veilige koppelingen:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is).

Het verschil tussen deze twee elementen is niet duidelijk wanneer u veilige koppelingen beheert in het beveiligings- & compliancecentrum:

- Wanneer u een beleid voor veilige koppelingen maakt, maakt u een veilige koppelingsregel en het bijbehorende beleid voor veilige koppelingen op hetzelfde moment met dezelfde naam voor beide.
- Wanneer u een beleid voor veilige koppelingen wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de regel voor veilige koppelingen. Alle andere instellingen wijzigen het beleid voor gekoppelde veilige koppelingen.
- Wanneer u een beleid voor veilige koppelingen verwijdert, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Exchange Online PowerShell of zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) gebruiken voor het configureren van beleidsregels voor veilige koppelingen verderop in dit artikel voor meer informatie.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Veilige koppelingen wilt** gaan, gebruikt u <https://protection.office.com/safelinksv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u beleidsregels voor veilige koppelingen wilt maken, wijzigen  en verwijderen, moet u lid zijn van de rollengroepen  Organisatiebeheer of Beveiligingsbeheerder in het Beveiligings- & **Compliancecentrum** en lid zijn van de rollengroep Organisatiebeheer in Exchange Online. 
  - Als u alleen-lezen toegang wilt tot beleidsregels voor veilige koppelingen, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie Machtigingen [in het Beveiligings-](permissions-in-the-security-and-compliance-center.md) & Compliancecentrum en [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo)voor meer informatie.

  > [!NOTE]
  > 
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  . - De **rollengroep Alleen-weergeven voor** organisatiebeheer in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de functie.

- Zie Beleidsinstellingen voor veilige koppelingen voor onze aanbevolen instellingen voor beleid voor veilige [koppelingen.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.

- [Er worden voortdurend nieuwe functies toegevoegd aan Microsoft Defender voor Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleid voor veilige koppelingen aanpassen.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Gebruik het beveiligings- & compliancecentrum om beleidsregels voor veilige koppelingen te maken

Als u een aangepast beleid voor veilige koppelingen maakt in het Beveiligings- & Compliancecentrum, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen tegelijk gemaakt met dezelfde naam voor beide.

1. Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Links**.

2. Klik op **de pagina Veilige** koppelingen op **Maken.**

3. De **wizard Nieuw beleid voor veilige** koppelingen wordt geopend. Configureer **op de pagina** Naam uw beleid de volgende instellingen:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Wanneer u klaar bent, klikt u op **Volgende.**

4. Configureer **de** volgende instellingen op de pagina Instellingen die wordt weergegeven:

   - **Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten:** Selecteer **Aan** om beveiliging van veilige koppelingen in te stellen voor koppelingen in e-mailberichten.

   - **Selecteer de actie voor onbekende of potentieel schadelijke URL's in Microsoft Teams:** Selecteer **Aan** om beveiliging van veilige koppelingen in te stellen voor koppelingen in Teams.

   - **Realtime URL-scan toepassen** op verdachte koppelingen en koppelingen die naar bestanden wijzen: Selecteer deze instelling om het scannen van koppelingen in e-mailberichten in realtime mogelijk te maken.

   - **Wacht totdat URL-scannen is** voltooid voordat het bericht wordt weergegeven: Selecteer deze instelling om te wachten totdat het scannen van url's in realtime is voltooid voordat het bericht wordt weergegeven.

   - **Veilige koppelingen toepassen op e-mailberichten** die binnen de organisatie zijn verzonden: Selecteer deze instelling om het beleid voor veilige koppelingen toe te passen op berichten tussen interne afzenders en interne geadresseerden.

   - **Gebruikersklikken niet bijhouden:** laat deze instelling niet geselecteerd om het bijhouden van gebruikersklikken op URL's in e-mailberichten in te stellen.

   - **Gebruikers mogen niet doorklikken** naar de oorspronkelijke URL: Selecteer deze instelling om te blokkeren dat gebruikers doorklikken naar de oorspronkelijke URL op [waarschuwingspagina's.](safe-links.md#warning-pages-from-safe-links)

   - **De volgende URL's niet** opnieuw schrijven: Hiermee krijgt u toegang tot de opgegeven URL's die anders zouden worden geblokkeerd door veilige koppelingen.

     Typ in het vak de URL of waarde die u wilt gebruiken en klik op ![Knoppictogram toevoegen](../../media/ITPro-EAC-AddIcon.png).

     Als u een bestaand item wilt verwijderen, selecteert u deze en klikt u op ![Pictogram knop Verwijderen](../../media/ITPro-EAC-DeleteIcon.png).

     Zie De syntaxis van de vermelding voor de lijst 'De volgende URL's niet opnieuw [schrijven'.](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Zie Instellingen voor veilige koppelingen voor [e-mailberichten](safe-links.md#safe-links-settings-for-email-messages) en Instellingen voor veilige koppelingen voor Microsoft Teams voor meer [informatie over deze instellingen.](safe-links.md#safe-links-settings-for-microsoft-teams)

   Zie Beleidsinstellingen voor veilige koppelingen voor meer aanbevolen waarden voor standaard- en strikte [beleidsinstellingen.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

   Wanneer u klaar bent, klikt u op **Volgende.**

5. Op de **pagina Toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden op wie het beleid van toepassing is.

   U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

   Klik **op Een voorwaarde toevoegen.** Selecteer in de vervolgkeuzekeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**

   - **De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.
   - **De geadresseerde is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.
   - **Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.

   Nadat u de voorwaarde hebt geselecteerd, wordt er een bijbehorende vervolgkeuze weergegeven met een **Van deze vakjes.**

   - Klik in het vak en blader door de lijst met waarden die u wilt selecteren.
   - Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.
   - Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.
   - Als u afzonderlijke items wilt verwijderen, klikt **u op Pictogram** Verwijderen verwijderen op de ![ ](../../media/scc-remove-icon.png) waarde.
   - Als u de hele voorwaarde wilt verwijderen, klikt **u op Pictogram** Verwijderen in de ![ ](../../media/scc-remove-icon.png) voorwaarde.

   Als u een extra voorwaarde wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.

   Als u uitzonderingen wilt toevoegen, klikt **u op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Wanneer u klaar bent, klikt u op **Volgende.**

6. Controleer uw **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven. U kunt op **Bewerken op elke** instelling klikken om deze te wijzigen.

   Wanneer u klaar bent, klikt u op **Voltooien.**

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige koppelingen weer te geven

1. Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Links**.

2. Selecteer op **de pagina** Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).

   De beleidsdetails worden weergegeven in een fly-out

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Gebruik het beveiligings- & compliancecentrum om beleidsregels voor veilige koppelingen te wijzigen

1. Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Links**.

2. Selecteer op **de pagina** Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in de beleidsdetails die worden weergegeven op **Beleid bewerken.**

De beschikbare instellingen in de fly-out die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in de sectie Het beveiligings- [& compliancecentrum](#use-the-security--compliance-center-to-create-safe-links-policies) gebruiken om beleidsregels voor veilige koppelingen te maken.

Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.

### <a name="enable-or-disable-safe-links-policies"></a>Beleidsregels voor veilige koppelingen in- of uitschakelen

1. Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Links**.

2. Let op de waarde in de **kolom Status:**

   - Verplaats te wisselknop naar links om het beleid uit te schakelen: ![Beleid uitschakelen](../../media/scc-toggle-off.png).

   - Verplaats te wisselknop naar rechts om het beleid in te schakelen: ![Beleid in-/uit-](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>De prioriteit van beleidsregels voor veilige koppelingen instellen

Beleidsregels voor veilige koppelingen krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere agenten hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Beleidsregels voor veilige koppelingen worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).

> [!NOTE]
> In het & compliancecentrum kunt u alleen de prioriteit van het beleid voor veilige koppelingen wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de regel veilige koppelingen maakt (die van invloed kan zijn op de prioriteit van bestaande regels).

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Links**.

2. Selecteer op **de pagina** Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in de beleidsdetails die worden weergegeven op de beschikbare prioriteitsknop:

   - In het beleid Veilige koppelingen met **prioriteit 0** is alleen de **knop Prioriteit verlagen** beschikbaar. 

   - In het beleid Veilige koppelingen met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** is alleen de knop **Prioriteit verhogen** beschikbaar.

   - Als u drie of meer beleidsregels voor veilige koppelingen hebt,  hebben  beleidsregels tussen de waarden met de hoogste en laagste prioriteit zowel de knoppen Prioriteit verhogen als Prioriteit verlagen beschikbaar.

4. Klik **op Prioriteit verhogen of** Prioriteit verlagen **om** de waarde Prioriteit **te** wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Het beveiligings- & compliancecentrum gebruiken om beleid voor veilige koppelingen te verwijderen

1. Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Links**.

2. Selecteer op **de pagina** Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in de beleidsdetails die worden weergegeven op Beleid verwijderen **en** klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om beleid voor veilige koppelingen te configureren

Zoals eerder beschreven, bestaat een beleid voor veilige koppelingen uit een beleid voor veilige koppelingen en een regel voor veilige koppelingen.

In PowerShell is het verschil tussen beleidsregels voor veilige koppelingen en regels voor veilige koppelingen duidelijk. U beheert beleidsregels voor veilige koppelingen met behulp van **\* de cmdlets -SafeLinksPolicy** en u beheert regels voor veilige koppelingen met behulp van **\* de cmdlets -SafeLinksRule.**

- In PowerShell maakt u eerst het beleid voor veilige koppelingen en vervolgens maakt u de regel voor veilige koppelingen waarin het beleid wordt aangegeven waar de regel op van toepassing is.
- In PowerShell wijzigt u de instellingen in het beleid voor veilige koppelingen en de regel voor veilige koppelingen afzonderlijk.
- Wanneer u een beleid voor veilige koppelingen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-safe-links-policies"></a>PowerShell gebruiken om beleid voor veilige koppelingen te maken

Het maken van een beleid voor veilige koppelingen in PowerShell is een proces in twee stappen:

1. Maak het beleid voor veilige koppelingen.
2. Maak de regel veilige koppelingen die het beleid voor veilige koppelingen aangeeft waar de regel op van toepassing is.

> [!NOTE]
> 
> - U kunt een nieuwe regel voor veilige koppelingen maken en er een bestaand, niet-verbonden beleid voor veilige koppelingen aan toewijzen. Een veilige koppelingsregel kan niet worden gekoppeld aan meer dan één beleid voor veilige koppelingen.
> 
> - U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige koppelingen in PowerShell die pas beschikbaar zijn in het Beveiligings- & Compliancecentrum nadat u het beleid hebt gemaakt:
> 
>   - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **Nieuw-SafeLinksRule).**
>   - Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-SafeLinksRule).**
> 
> - Een nieuw beleid voor veilige koppelingen dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum als u het beleid aan een regel voor veilige koppelingen toewijst.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken

Gebruik de volgende syntaxis om een beleid voor veilige koppelingen te maken:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Zie De [syntaxis](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)van de vermelding voor de volgende URL's niet opnieuw schrijven voor meer informatie over de syntaxis van de invoer die u wilt gebruiken voor de parameter _DoNotRewriteUrls._
> 
> - Zie de sectie [PowerShell](#use-powershell-to-modify-safe-links-policies) gebruiken om beleidsregels voor veilige koppelingen te wijzigen verderop in dit artikel voor aanvullende syntaxis die u kunt gebruiken voor de parameter _DoNotRewriteUrls_ wanneer u bestaande beleidsregels voor veilige koppelingen wijzigt met de cmdlet **Set-SafeLinksPolicy.**

In dit voorbeeld wordt een beleid voor veilige koppelingen met de naam Contoso All gemaakt met de volgende waarden:

- Schakel URL's scannen en herschrijven in e-mailberichten in.
- URL's scannen in teams in-/uit-/uit -2 zetten (alleen TAP Preview).
- Schakel realtime scannen in van geklikte URL's, inclusief geklikte koppelingen die naar bestanden wijzen.
- Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt.
- Schakel URL's scannen en herschrijven in voor interne berichten.
- Gebruikersklikken bijhouden die betrekking hebben op beveiliging tegen veilige koppelingen (we gebruiken de parameter _DoNotTrackUserClicks_ niet en de standaardwaarde is $false, wat betekent dat gebruikersklikken worden bijgespoord).
- Gebruikers mogen niet doorklikken naar de oorspronkelijke URL.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Zie [Nieuw-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Stap 2: PowerShell gebruiken om een regel voor veilige koppelingen te maken

Als u een regel voor veilige koppelingen wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In dit voorbeeld wordt een veilige koppelingsregel met de naam Contoso All gemaakt met de volgende voorwaarden:

- De regel is gekoppeld aan het beleid voor veilige koppelingen met de naam Contoso All.
- De regel is van toepassing op alle geadresseerden in het contoso.com domein.
- Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.
- De regel is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Zie [Nieuw-SafeLinksRule](/powershell/module/exchange/new-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen weer te geven

Gebruik de volgende syntaxis als u bestaand beleid voor veilige koppelingen wilt weergeven:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle beleidsregels voor veilige koppelingen weergegeven.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

Dit voorbeeld retourneert gedetailleerde informatie voor het beleid voor veilige koppelingen met de naam Contoso Executives.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Zie [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen weer te geven

Als u bestaande regels voor veilige koppelingen wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle regels voor veilige koppelingen weergegeven.

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

Dit voorbeeld retourneert gedetailleerde informatie voor de regel voor veilige koppelingen met de naam Contoso Executives.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Zie [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen te wijzigen

U kunt de naam van een beleid voor veilige koppelingen niet wijzigen in PowerShell (de cmdlet **Set-SafeLinksPolicy** heeft geen _naamparameter)._ Wanneer u de naam van een beleid voor veilige koppelingen wijzigt in het beveiligings- & compliancecentrum, wijzigt u alleen de naam van de regel voor veilige _koppelingen._

De enige extra overweging voor het wijzigen van beleidsregels voor veilige koppelingen in PowerShell is de beschikbare syntaxis voor de parameter _DoNotRewriteUrls_ (de lijst 'De volgende URL's niet [herschrijven'):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- Als u waarden wilt toevoegen die bestaande vermeldingen vervangen, gebruikt u de volgende syntaxis: `"Entry1","Entry2,..."EntryN"` .
- Als u waarden wilt toevoegen of verwijderen zonder dat dit van invloed is op andere bestaande vermeldingen, gebruikt u de volgende syntaxis: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Anders zijn dezelfde instellingen beschikbaar wanneer u een beleid voor veilige koppelingen maakt, zoals beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) gebruiken om eerder in dit artikel een beleidssectie voor veilige koppelingen te maken.

Als u een beleid voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen te wijzigen

De enige instelling die niet beschikbaar is wanneer u een regel voor veilige koppelingen in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor veilige koppelingen wilt in- of uitschakelen.

Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) gebruiken om eerder in dit artikel een sectie met veilige koppelingen te maken.

Als u een regel voor veilige koppelingen wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Zie [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen in of uit te schakelen

Als u een regel voor veilige koppelingen in PowerShell in- of uitschakelen, wordt het hele beleid voor veilige koppelingen (de regel voor veilige koppelingen en het toegewezen beleid voor veilige koppelingen) in- of uitgeschakeld.

Als u een regel voor veilige koppelingen in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling uitgeschakeld.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Zie Enable-SafeLinksRule and Disable-SafeLinksRule [(Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule)](/powershell/module/exchange/disable-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>PowerShell gebruiken om de prioriteit van regels voor veilige koppelingen in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit van een regel voor veilige koppelingen in PowerShell wilt instellen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de **cmdlet Nieuw-SafeLinksRule.**

Zie [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen te verwijderen

Wanneer u PowerShell gebruikt om een beleid voor veilige koppelingen te verwijderen, wordt de bijbehorende regel voor veilige koppelingen niet verwijderd.

Als u een beleid voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het beleid voor veilige koppelingen met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Zie [Remove-SafeLinksPolicy (Verwijderen-SafeLinksPolicy)](/powershell/module/exchange/remove-safelinkspolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen te verwijderen

Wanneer u PowerShell gebruikt om een veilige koppelingsregel te verwijderen, wordt het bijbehorende beleid voor veilige koppelingen niet verwijderd.

Als u een regel voor veilige koppelingen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Zie [Remove-SafeLinksRule voor](/powershell/module/exchange/remove-safelinksrule)gedetailleerde syntaxis- en parametergegevens.

Als u wilt controleren of veilige koppelingen berichten scannen, controleert u de beschikbare Microsoft Defender voor Office 365-rapporten. Zie Rapporten voor Defender voor [Office 365](view-reports-for-mdo.md) en Verkenner gebruiken in het beveiligings- [& compliancecentrum voor meer informatie.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga als volgt te werk om te controleren of u beleidsregels voor veilige koppelingen hebt gemaakt, gewijzigd of verwijderd:

- Ga in & Beveiligingscentrum naar **Beveiligingsbeheerbeleid** \>  \> **ATP Safe Links**. Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.** Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.

- Vervang in Exchange Online PowerShell of Exchange Online Protection PowerShell de naam van het beleid of de regel, voer de volgende opdracht uit en controleer \<Name\> de instellingen:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```