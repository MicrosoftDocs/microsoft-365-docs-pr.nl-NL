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
ms.openlocfilehash: 71ea33f1f6fbebf6d87a4b42ad3bd96a60597b90
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166265"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Beleid voor veilige koppelingen instellen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben. Als u een thuisgebruiker bent en op zoek bent naar informatie over Safelinks in Outlook, gaat u naar [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Veilige koppelingen is een functie in Microsoft Defender voor [Office 365](office-365-atp.md) waarmee de URL wordt gescand van binnenkomende e-mailberichten in de e-mailstroom en het tijdstip van klikverificatie van URL's en koppelingen in e-mailberichten en op andere locaties. Zie Veilige koppelingen [in Microsoft Defender voor Office 365](atp-safe-links.md)voor meer informatie.

Er is geen ingebouwd of standaardbeleid voor veilige koppelingen. Voor het scannen van URL's met veilige koppelingen moet u een of meer beleidsregels voor veilige koppelingen maken, zoals wordt beschreven in dit artikel.

> [!NOTE]
> U configureert de algemene instellingen voor beveiliging tegen veilige koppelingen **buiten het** beleid voor veilige koppelingen. Zie Algemene instellingen [configureren voor veilige koppelingen in Microsoft Defender voor Office 365](configure-global-settings-for-safe-links.md)voor instructies.

U kunt beleid voor veilige koppelingen configureren in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Microsoft Defender voor Office 365-invoegabonnementen).

De basiselementen van een beleid voor veilige koppelingen zijn:

- Het beleid voor veilige **koppelingen:** schakel beveiliging voor veilige koppelingen in, schakel HET scannen van realtime-URL's in, geef op of er moet worden gewacht totdat realtime scannen is voltooid voordat het bericht wordt verzonden, geef de scanfunctie voor interne berichten in, geef op of gebruikersklikken op URL's moeten worden bij te houden en geef op of gebruikers moeten klikken op een overbezorging tot de oorspronkelijke URL.
- **De regel voor veilige koppelingen:** hiermee geeft u de prioriteit- en geadresseerdefilters op (op wie het beleid van toepassing is).

Het verschil tussen deze twee elementen is niet duidelijk wanneer u het beleid voor veilige koppelingen beheert in het & compliancecentrum:

- Wanneer u een beleid voor veilige koppelingen maakt, maakt u tegelijkertijd een regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen met dezelfde naam voor beide.
- Wanneer u een beleid voor veilige koppelingen wijzigt, worden instellingen met betrekking tot de naam, prioriteit, in- of uitgeschakeld en geadresseerdenfilters de regel voor veilige koppelingen gewijzigd. Alle andere instellingen wijzigen het bijbehorende beleid voor veilige koppelingen.
- Wanneer u een beleid voor veilige koppelingen verwijdert, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Exchange Online PowerShell of de zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) gebruiken om beleidsregels voor veilige koppelingen verderop in dit artikel te configureren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Veilige koppelingen wilt** gaan, gebruikt u <https://protection.office.com/safelinksv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet machtigingen toegewezen krijgen voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u beleidsregels voor veilige koppelingen wilt maken, wijzigen  en  verwijderen, moet u lid zijn van  de rollengroepen Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- &-compliancecentrum en lid zijn van de rollengroep Organisatiebeheer in Exchange Online. 
  - Voor alleen-lezen toegang tot beleidsregels voor veilige koppelingen  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie Machtigingen in [het beveiligings-](permissions-in-the-security-and-compliance-center.md) en & en [machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)voor meer informatie.

  > [!NOTE]
  > 
  > - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  . - De **rollengroep Organisatiebeheer alleen-weergeven** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de functie.

- Zie beleidsinstellingen voor veilige koppelingen voor onze [aanbevolen instellingen voor het beleid voor veilige koppelingen.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- Het kan 30 minuten duren voordat een nieuw of bijgewerkt beleid wordt toegepast.

- [Nieuwe functies worden voortdurend toegevoegd aan Microsoft Defender voor Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) Als er nieuwe functies worden toegevoegd, moet u mogelijk uw bestaande beleidsregels voor veilige koppelingen aanpassen.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Het beveiligings- & gebruiken om beleid voor veilige koppelingen te maken

Als u een aangepast beleid voor veilige koppelingen maakt in het beveiligings- & compliancecentrum, worden de regel voor veilige koppelingen en het bijbehorende beleid voor veilige koppelingen op hetzelfde moment met dezelfde naam voor beide gemaakt.

1. Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**

2. Klik op **de pagina Veilige** koppelingen op **Maken.**

3. De **wizard Nieuw beleid voor veilige** koppelingen wordt geopend. Configureer **de volgende instellingen op** de pagina Uw beleid een naam geven:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Klik op Volgende wanneer u klaar **bent.**

4. Configureer **de volgende** instellingen op de pagina Instellingen die wordt weergegeven:

   - **Selecteer de actie voor onbekende, mogelijk schadelijke URL's in** berichten: Selecteer **Aan** om beveiliging tegen veilige koppelingen in te stellen voor koppelingen in e-mailberichten.

   - **Selecteer de actie voor onbekende of mogelijk** schadelijke  URL's in Microsoft Teams: Selecteer Aan om beveiliging tegen veilige koppelingen in te stellen voor koppelingen in Teams.

   - **Realtime-URL's scannen** op verdachte koppelingen en koppelingen naar bestanden: Selecteer deze instelling om het scannen van koppelingen in e-mailberichten in realtime mogelijk te maken.

   - **Wacht totdat het scannen van de URL** is voltooid voordat het bericht wordt weergegeven. Selecteer deze instelling om te wachten totdat het scannen van realtime-URL's is voltooid voordat het bericht wordt weergegeven.

   - **Veilige koppelingen toepassen op e-mailberichten** die binnen de organisatie worden verzonden: selecteer deze instelling om het beleid voor veilige koppelingen toe te passen op berichten tussen interne afzenders en interne geadresseerden.

   - **Klikken door gebruikers niet bijhouden:** laat deze instelling uitgeschakeld om het bijhouden van klikken door gebruikers op URL's in e-mailberichten mogelijk te maken.

   - **Niet toestaan dat gebruikers doorklikken** naar de oorspronkelijke URL: Selecteer deze instelling om te blokkeren dat gebruikers doorklikken naar de oorspronkelijke URL op waarschuwingspagina's. [](atp-safe-links.md#warning-pages-from-safe-links)

   - **Herschrijf de volgende URL's** niet: hiermee geeft u toegang tot de opgegeven URL's die anders worden geblokkeerd door veilige koppelingen.

     Typ in het vak de URL of waarde die u wilt gebruiken en klik vervolgens op ![Knoppictogram Toevoegen](../../media/ITPro-EAC-AddIcon.png).

     Als u een bestaande vermelding wilt verwijderen, selecteert u deze en klikt u op ![Knoppictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.png).

     Zie de syntaxis voor invoer voor de lijst 'De volgende URL's niet opnieuw [schrijven'.](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Zie instellingen voor veilige [](atp-safe-links.md#safe-links-settings-for-email-messages) koppelingen voor e-mailberichten en instellingen voor veilige koppelingen voor Microsoft Teams voor meer [informatie over deze instellingen.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)

   Zie beleidsinstellingen voor veilige koppelingen voor meer informatie over de aanbevolen waarden voor standaard- [en strikte beleidsinstellingen.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

   Klik op Volgende wanneer u klaar **bent.**

5. Zoek op **de** pagina Toegepast op die wordt weergegeven de interne geadresseerden op wie het beleid van toepassing is.

   U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

   Klik **op Voorwaarde toevoegen.** Selecteer in de vervolgkeuzepkeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**

   - **De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.
   - **De geadresseerde is lid van:** Geeft een of meer groepen in uw organisatie op.
   - **Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.

   Nadat u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzekeuze verschijnen met een **Van deze** vakjes.

   - Klik in het vak en blader door de lijst met waarden die u wilt selecteren.
   - Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.
   - Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.
   - Als u afzonderlijke items wilt verwijderen, klikt **u op het pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) waarde.
   - Als u de hele voorwaarde wilt verwijderen, klikt **u op het pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) voorwaarde.

   Als u een extra voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als.**

   Als u uitzonderingen wilt toevoegen, klikt u **op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als.** De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Klik op Volgende wanneer u klaar **bent.**

6. Controleer de **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven. U kunt bij **elke** instelling op Bewerken klikken om deze te wijzigen.

   Klik op Voltooien wanneer u **klaar bent.**

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige koppelingen weer te geven

1. Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**

2. Selecteer op **de** pagina Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).

   De beleidsdetails worden in een fly-out weergegeven

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige koppelingen te wijzigen

1. Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**

2. Selecteer op **de** pagina Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in het fly-out met beleidsdetails op **Beleid bewerken.**

De beschikbare instellingen in de fly out die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in het compliancecentrum voor het gebruik van het [beveiligings- &](#use-the-security--compliance-center-to-create-safe-links-policies) om beleidsregels voor veilige koppelingen te maken.

Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteit wilt instellen.

### <a name="enable-or-disable-safe-links-policies"></a>Beleid voor veilige koppelingen in- of uitschakelen

1. Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**

2. U ziet de waarde in de **kolom Status:**

   - Verplaats te wisselknop naar links om het beleid uit te schakelen: ![Beleid uitschakelen](../../media/scc-toggle-off.png).

   - Verplaats te wisselknop naar rechts om het beleid in te schakelen: ![Beleid in-/uit](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>De prioriteit van beleidsregels voor veilige koppelingen instellen

Standaard krijgen beleidsregels voor veilige koppelingen een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Beleidsregels voor veilige koppelingen worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).

> [!NOTE]
> In het & compliancecentrum kunt u de prioriteit van het beleid voor veilige koppelingen alleen wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de regel voor veilige koppelingen maakt (die van invloed kan zijn op de prioriteit van bestaande regels).

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**

2. Selecteer op **de** pagina Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in de weergegeven beleidsdetails op de beschikbare prioriteitknop:

   - Voor het beleid veilige koppelingen **met** prioriteitwaarde **0** is alleen **de** knop Prioriteit verlagen beschikbaar.

   - Voor het beleid veilige koppelingen met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** is alleen de knop Prioriteit **verhogen** beschikbaar.

   - Als u drie of meer beleidsregels voor veilige koppelingen hebt,  zijn voor beleid tussen de hoogste en laagste prioriteit de knoppen Hogere prioriteit en Lagere **prioriteit** beschikbaar.

4. Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Het beveiligings- & gebruiken om beleidsregels voor veilige koppelingen te verwijderen

1. Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.**

2. Selecteer op **de** pagina Veilige koppelingen een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in het weergegeven beleidsdetails op Beleid verwijderen en klik vervolgens op **Ja** in het dialoogvenster met de waarschuwing dat wordt weergegeven. 

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om beleidsregels voor veilige koppelingen te configureren

Zoals eerder is beschreven, bestaat een beleid voor veilige koppelingen uit een beleid voor veilige koppelingen en een regel voor veilige koppelingen.

In PowerShell is het verschil tussen beleidsregels voor veilige koppelingen en regels voor veilige koppelingen duidelijk. U beheert beleidsregels voor veilige koppelingen met behulp van de cmdlets **\* -SafeLinksPolicy** en u beheert regels voor veilige koppelingen met behulp van de cmdlets **\* -SafeLinksRule.**

- In PowerShell maakt u eerst het beleid voor veilige koppelingen en vervolgens maakt u de regel voor veilige koppelingen om aan te geven op welke beleidsregel de regel van toepassing is.
- In PowerShell wijzigt u de instellingen in het beleid voor veilige koppelingen en de regel voor veilige koppelingen afzonderlijk.
- Wanneer u een beleid voor veilige koppelingen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige koppelingen niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen te maken

Het maken van een beleid voor veilige koppelingen in PowerShell bestaat uit twee stappen:

1. Maak het beleid voor veilige koppelingen.
2. Maak de regel voor veilige koppelingen die het beleid voor veilige koppelingen aangeeft dat met de regel van toepassing is.

> [!NOTE]
> 
> - U kunt een nieuwe regel voor veilige koppelingen maken en een bestaand, niet-verbonden beleid voor veilige koppelingen aan de regel toewijzen. Een regel voor veilige koppelingen kan niet worden gekoppeld aan meer dan één beleid voor veilige koppelingen.
> 
> - U kunt de volgende instellingen configureren voor nieuw beleid voor veilige koppelingen in PowerShell die pas beschikbaar zijn in het beveiligings- & compliancecentrum nadat u het beleid hebt gemaakt:
> 
>   - Het nieuwe beleid maken dat is uitgeschakeld _(ingeschakeld_ `$false` op de cmdlet **New-SafeLinksRule).**
>   - De prioriteit van het beleid instellen tijdens het maken _(prioriteit)_ _\<Number\>_ op de cmdlet **New-SafeLinksRule).**
> 
> - Een nieuw beleid voor veilige koppelingen dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum wanneer u het beleid toewijst aan een regel voor veilige koppelingen.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Stap 1: PowerShell gebruiken om een beleid voor veilige koppelingen te maken

Gebruik de volgende syntaxis om een beleid voor veilige koppelingen te maken:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Zie de syntaxis voor Invoer voor de lijst 'De volgende URL's niet herschrijven' voor meer informatie over de [syntaxis](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)van de invoer die moet worden gebruikt voor de parameter _DoNotRewriteUrls._
> 
> - Voor aanvullende syntaxis die u kunt gebruiken voor de parameter _DoNotRewriteUrls_ wanneer u bestaande beleidsregels voor veilige koppelingen wijzigt met behulp van de cmdlet **Set-SafeLinksPolicy,** zie de sectie [PowerShell](#use-powershell-to-modify-safe-links-policies) gebruiken om beleidsregels voor veilige koppelingen verderop in dit artikel te wijzigen.

In dit voorbeeld wordt een beleid voor veilige koppelingen met de naam Contoso All gemaakt met de volgende waarden:

- Schakel URL's scannen en herschrijven in e-mailberichten in.
- URL's scannen in teams in turn on (TAP Preview only).
- Schakel realtime scannen in van geklikte URL's, inclusief geklikte koppelingen die naar bestanden wijzen.
- Wacht totdat het scannen van de URL is voltooid voordat het bericht wordt weergegeven.
- Schakel HET scannen en herschrijven van URL's in voor interne berichten.
- Klikken van gebruikers bijhouden met betrekking tot de beveiliging van veilige koppelingen (de parameter _DoNotTrackUserClicks_ wordt niet gebruikt en de standaardwaarde is $false, wat betekent dat klikken van gebruikers worden bij houden).
- Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Zie [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)voor gedetailleerde syntaxis- en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Stap 2: PowerShell gebruiken om een regel voor veilige koppelingen te maken

Gebruik de volgende syntaxis om een regel voor veilige koppelingen te maken:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In dit voorbeeld wordt een regel voor veilige koppelingen gemaakt met de naam Contoso All met de volgende voorwaarden:

- De regel is gekoppeld aan het beleid voor veilige koppelingen met de naam Contoso All.
- De regel is van toepassing op alle geadresseerden in contoso.com domein.
- Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.
- De regel is ingeschakeld (de parameter _Enabled_ wordt niet gebruikt en de standaardwaarde `$true` is).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Zie [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen weer te geven

Gebruik de volgende syntaxis om bestaand beleid voor veilige koppelingen te bekijken:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst van alle beleidsregels voor veilige koppelingen weergegeven.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

In dit voorbeeld wordt gedetailleerde informatie gegeven over het beleid voor veilige koppelingen, genaamd Contoso-leidinggevenden.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Zie [Get-SafeLinksPolicy voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)

### <a name="use-powershell-to-view-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen weer te geven

Gebruik de volgende syntaxis als u bestaande regels voor veilige koppelingen wilt weergeven:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst van alle regels voor veilige koppelingen weergegeven.

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

In dit voorbeeld wordt gedetailleerde informatie gegeven over de regel voor veilige koppelingen met de naam Contoso Leidinggevenden.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Zie [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen te wijzigen

U kunt de naam van een beleid voor veilige koppelingen in PowerShell niet wijzigen (de cmdlet **Set-SafeLinksPolicy** heeft geen _naamparameter)._ Wanneer u de naam van een beleid voor veilige koppelingen wijzigt in het beveiligings- & compliancecentrum, wijzigt u alleen de naam van de regel voor veilige _koppelingen._

De enige extra overweging voor het wijzigen van beleidsregels voor veilige koppelingen in PowerShell is de beschikbare syntaxis voor de parameter _DoNotRewriteUrls_ (de lijst 'De volgende URL's niet opnieuw [schrijven'):](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- Gebruik de volgende syntaxis om waarden op te voegen die eventuele bestaande items `"Entry1","Entry2,..."EntryN"` vervangen:
- Gebruik de volgende syntaxis om waarden toe te voegen of te verwijderen zonder dat dit van invloed is op andere bestaande gegevens: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Anders zijn dezelfde instellingen beschikbaar wanneer u een beleid voor veilige koppelingen maakt, zoals wordt beschreven in stap [1: Gebruik PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) om een beleidssectie voor veilige koppelingen te maken eerder in dit artikel.

Gebruik de volgende syntaxis om een beleid voor veilige koppelingen te wijzigen:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-SafeLinksPolicy voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)

### <a name="use-powershell-to-modify-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen te wijzigen

De enige instelling die niet beschikbaar is wanneer u een regel voor veilige koppelingen wijzigt in PowerShell, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor veilige koppelingen wilt in- of uitschakelen.

Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt, zoals wordt beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) gebruiken om een sectie met regels voor veilige koppelingen te maken eerder in dit artikel.

Gebruik de volgende syntaxis om een regel voor veilige koppelingen te wijzigen:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Zie [Set-SafeLinksRule voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)syntaxis- en parameterinformatie.

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen in of uit te schakelen

Als u een regel voor veilige koppelingen in PowerShell in- of uit schakelen, wordt het hele beleid voor veilige koppelingen (de regel voor veilige koppelingen en het toegewezen beleid voor veilige koppelingen) in- of uitgeschakeld.

Gebruik de volgende syntaxis om een regel voor veilige koppelingen in PowerShell in of uit te schakelen:

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

Zie [Enable-SafeLinksRule en Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) voor gedetailleerde syntaxis- en [parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>PowerShell gebruiken om de prioriteit van regels voor veilige koppelingen in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Gebruik de volgende syntaxis om de prioriteit van een regel voor veilige koppelingen in PowerShell in te stellen:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-SafeLinksRule.**

Zie [Set-SafeLinksRule voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)syntaxis- en parameterinformatie.

### <a name="use-powershell-to-remove-safe-links-policies"></a>PowerShell gebruiken om beleidsregels voor veilige koppelingen te verwijderen

Wanneer u PowerShell gebruikt om een beleid voor veilige koppelingen te verwijderen, wordt de bijbehorende regel voor veilige koppelingen niet verwijderd.

Gebruik de volgende syntaxis om een beleid voor veilige koppelingen in PowerShell te verwijderen:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het beleid voor veilige koppelingen met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Zie [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-remove-safe-links-rules"></a>PowerShell gebruiken om regels voor veilige koppelingen te verwijderen

Wanneer u PowerShell gebruikt om een regel voor veilige koppelingen te verwijderen, wordt het bijbehorende beleid voor veilige koppelingen niet verwijderd.

Gebruik de volgende syntaxis om een regel voor veilige koppelingen in PowerShell te verwijderen:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de regel voor veilige koppelingen met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Zie [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)voor gedetailleerde syntaxis- en parameterinformatie.

Als u wilt controleren of veilige koppelingen berichten scannen, controleert u de beschikbare Microsoft Defender voor Office 365-rapporten. Zie Rapporten voor Defender voor [Office 365](view-reports-for-atp.md) en Verkenner weergeven in het beveiligings- & [compliancecentrum voor](threat-explorer.md)meer informatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga op een van de volgende stappen te werk om te controleren of u een beleid voor veilige koppelingen hebt gemaakt, gewijzigd of verwijderd:

- Ga in het & compliancecentrum naar Veilige koppelingen **van** ATP voor \>  \> **risicobeheerbeleid.** Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.** Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.

- Vervang in Exchange Online PowerShell of Exchange Online Protection PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
