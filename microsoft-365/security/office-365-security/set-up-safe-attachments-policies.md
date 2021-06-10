---
title: Het beleid Safe bijlagen instellen in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Meer informatie over het definiëren van Safe bijlagenbeleid om uw organisatie te beschermen tegen schadelijke bestanden in e-mail.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204655"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Het beleid Safe bijlagen instellen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](whats-new-in-defender-for-office-365.md) hebben. Als u een thuisgebruiker bent die informatie zoekt over het scannen van bijlagen in Outlook, gaat u naar [Geavanceerde Outlook.com-beveiliging.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Safe Bijlagen is een functie in [Microsoft Defender](whats-new-in-defender-for-office-365.md) voor Office 365 die een virtuele omgeving gebruikt om bijlagen in binnenkomende e-mailberichten te controleren nadat ze zijn gescand door [anti-malwarebeveiliging in Exchange Online Protection (EOP),](anti-malware-protection.md)maar vóór de bezorging aan geadresseerden. Zie voor meer informatie [Safe Bijlagen in Microsoft Defender voor Office 365.](safe-attachments.md)

Er is geen ingebouwd of standaardbeleid Safe bijlagen. Als u Safe bijlagen van e-mailbijlagen wilt scannen, moet u een of meer Safe bijlagenbeleid maken, zoals in dit artikel wordt beschreven.

U kunt Safe Bijlagen-beleid configureren in het beveiligings- & compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Defender voor Office 365-invoegabonnementen).

De basiselementen van een Safe bijlagenbeleid zijn:

- **Het beleid** voor veilige bijlagen: geeft de acties voor onbekende malwaredetecties op, of berichten met malwarebijlagen naar een opgegeven e-mailadres moeten worden verzonden en of berichten moeten worden verzonden als Safe Bijlagen scannen niet kan worden voltooid.
- **De veilige bijlageregel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is).

Het verschil tussen deze twee elementen is niet duidelijk wanneer u de Safe bijlagen beheert in het Beveiligings- & Compliancecentrum:

- Wanneer u een Safe-bijlagebeleid maakt, maakt u tegelijkertijd een veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen met dezelfde naam voor beide.
- Wanneer u een Safe bijlagenbeleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de veilige bijlageregel. Alle andere instellingen wijzigen het bijbehorende beleid voor veilige bijlagen.
- Wanneer u een Safe bijlagebeleid verwijdert, worden de veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Use [Exchange Online PowerShell Safe standalone EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) voor meer informatie.

> [!NOTE]
> In het gebied met algemene instellingen Safe bijlagen configureert u functies die niet afhankelijk zijn van Safe bijlagenbeleid. Zie Safe Bijlagen in [SharePoint, OneDrive](turn-on-mdo-for-spo-odb-and-teams.md) en Microsoft Teams en Safe in Microsoft 365 E5 voor [instructies.](safe-docs.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina Safe **bijlagen** wilt gaan, gebruikt u <https://protection.office.com/safeattachmentv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet machtigingen hebben toegewezen voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u beleidsregels voor Safe bijlagen wilt maken, wijzigen en  verwijderen, moet u lid zijn van de rollengroepen Organisatiebeheer  of Beveiligingsbeheerder in het beveiligings- & compliancecentrum en lid zijn van de rollengroep Organisatiebeheer in Exchange Online.  
  - Als u alleen-lezen toegang wilt tot Safe-bijlagenbeleid, moet  u lid  zijn van de rollengroepen Globale lezer of Beveiligingslezer in het beveiligings- & Compliancecentrum.

  Zie Machtigingen [in het Beveiligings-](permissions-in-the-security-and-compliance-center.md) & Compliancecentrum en [Machtigingen in](/exchange/permissions-exo/permissions-exo)Exchange Online.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie voor onze aanbevolen instellingen voor Safe bijlagenbeleid [de Safe Bijlagen.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Het beveiligings- & compliancecentrum gebruiken om Safe bijlagenbeleid te maken

Als u een aangepast Safe-bijlagebeleid maakt in het beveiligings- & compliancecentrum, worden de veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen tegelijk gemaakt met dezelfde naam voor beide.

1. Ga in het & Compliancecentrum naar **ATP** voor bedreigingsbeheerbeleid \>  \> **Safe Bijlagen.**

2. Klik op **Safe pagina Bijlagen** op **Maken.**

3. De **wizard Nieuw Safe bijlagenbeleid** wordt geopend. Configureer **op de pagina** Naam uw beleid de volgende instellingen:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Wanneer u gereed bent, klikt u op **Volgende**.

4. Configureer **op Instellingen** pagina die wordt weergegeven de volgende instellingen:

   - **Safe Antwoord op onbekende malware bijlagen:** Selecteer een van de volgende waarden:

     - **Uit:** Deze waarde wordt meestal niet aanbevolen.
     - **Monitor**
     - **Blok:** Dit is de standaardwaarde en de aanbevolen waarde in standaard- en strikt [vooraf ingestelde beveiligingsbeleidsregels.](preset-security-policies.md)
     - **Vervangen**
     - **Dynamische bezorging (voorbeeldfunctie)**

     Deze waarden worden uitgelegd in [Safe instellingen voor bijlagenbeleid.](safe-attachments.md#safe-attachments-policy-settings)

   - Verzend de bijlage naar het volgende e-mailadres: Voor de actiewaarden  **Blokkeren,** Controleren of Vervangen **kunt** u Omleiding inschakelen selecteren om berichten te verzenden die malwarebijlagen bevatten naar het opgegeven interne of externe e-mailadres voor analyse en onderzoek.  

     De aanbeveling voor standaard- en strikte beleidsinstellingen is om omleiding in te stellen. Zie de instellingen Safe [Bijlagen voor meer informatie.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

   - Pas de bovenstaande selectie toe als **er malware** wordt gescand op bijlagen of er een fout optreedt: De actie die is opgegeven door **Safe Attachments unknown malware response** wordt uitgevoerd op berichten, zelfs wanneer Safe Bijlagen scannen niet kan worden voltooid. Als u deze optie hebt geselecteerd, selecteert u altijd **Ingeschakeld omleiden.** Anders kunnen berichten verloren gaan.

   Wanneer u gereed bent, klikt u op **Volgende**.

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

   Wanneer u gereed bent, klikt u op **Volgende**.

6. Controleer uw **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven. U kunt op **Bewerken op elke** instelling klikken om deze te wijzigen.

   Wanneer u klaar bent, klikt u op **Voltooien.**

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Het beveiligings- & compliancecentrum gebruiken om de Safe bijlagen weer te geven

1. Ga in het & Compliancecentrum naar **ATP** voor bedreigingsbeheerbeleid \>  \> **Safe Bijlagen.**

2. Selecteer op **Safe pagina Bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).

   De beleidsdetails worden weergegeven in een fly-out

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Het beveiligings- & compliancecentrum gebruiken om het beleid Safe bijlagen te wijzigen

1. Ga in het & Compliancecentrum naar **ATP** voor bedreigingsbeheerbeleid \>  \> **Safe Bijlagen.**

2. Selecteer op **Safe pagina Bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in de beleidsdetails die worden weergegeven op **Beleid bewerken.**

De beschikbare instellingen in de fly-out die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in het sectie [Beveiligings- & compliancecentrum](#use-the-security--compliance-center-to-create-safe-attachments-policies) gebruiken om Safe bijlagenbeleid te maken.

Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.

### <a name="enable-or-disable-safe-attachments-policies"></a>Het beleid voor bijlagen Safe in- of uitschakelen

1. Ga in het & Compliancecentrum naar **ATP** voor bedreigingsbeheerbeleid \>  \> **Safe Bijlagen.**

2. Let op de waarde in de **kolom Status:**

   - De schakelknop naar links verplaatsen ![Beleid uitschakelen](../../media/scc-toggle-off.png) om het beleid uit te schakelen.

   - De schakelknop naar rechts verplaatsen ![Beleid in-/uit-](../../media/scc-toggle-on.png) om het beleid in te stellen.

### <a name="set-the-priority-of-safe-attachments-policies"></a>De prioriteit van het Safe bijlagen instellen

Standaard krijgen Safe bijlagenbeleid een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere agenten hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Safe Bijlagenbeleid wordt weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0).

**Opmerking:** In het & compliancecentrum kunt u alleen de prioriteit van het Safe wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de veilige bijlageregel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het & Compliancecentrum naar **ATP** voor bedreigingsbeheerbeleid \>  \> **Safe Bijlagen.**

2. Selecteer op **Safe pagina Bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in de beleidsdetails die worden weergegeven op de beschikbare prioriteitsknop.

   - Het Safe bijlagebeleid met **prioriteitswaarde** **0** heeft alleen de knop Prioriteit **verlagen** beschikbaar.

   - Het Safe bijlagebeleid met de  laagste prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit** verhogen beschikbaar.

   - Als u drie of meer Safe bijlagenbeleid hebt, hebben beleidsregels tussen  de  waarden met de hoogste en laagste prioriteit zowel de knoppen Prioriteit verhogen als Prioriteit verlagen beschikbaar.

4. Klik **op Prioriteit verhogen of** Prioriteit verlagen **om** de waarde Prioriteit **te** wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Het beveiligings- & compliancecentrum gebruiken om Safe bijlagen te verwijderen

1. Ga in het & Compliancecentrum naar **ATP** voor bedreigingsbeheerbeleid \>  \> **Safe Bijlagen.**

2. Selecteer op **Safe pagina Bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in de beleidsdetails die worden weergegeven op Beleid verwijderen **en** klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om het Safe bijlagen te configureren

Zoals eerder beschreven, bestaat Safe bijlagebeleid uit een beleid voor veilige bijlagen en een veilige bijlageregel.

In PowerShell is het verschil tussen beleidsregels voor veilige bijlagen en regels voor veilige bijlagen duidelijk. U beheert beleidsregels voor veilige bijlagen met behulp van **\* de cmdlets -SafeAttachmentPolicy** en u beheert regels voor veilige bijlagen met de **\* cmdlets -SafeAttachmentRule.**

- In PowerShell maakt u eerst het beleid voor veilige bijlagen en vervolgens maakt u de veilige bijlageregel waarin het beleid wordt aangegeven waar de regel op van toepassing is.
- In PowerShell wijzigt u de instellingen in het beleid voor veilige bijlagen en de regel voor veilige bijlagen afzonderlijk.
- Wanneer u een veilig bijlagebeleid uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige bijlagen niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell gebruiken om een Safe te maken

Het maken van Safe bijlagebeleid in PowerShell is een proces in twee stappen:

1. Maak het beleid voor veilige bijlagen.
2. Maak de veilige bijlageregel die het beleid voor veilige bijlagen aangeeft waar de regel op van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe veilige bijlageregel maken en er een bestaand, niet-verbonden beleid voor veilige bijlagen aan toewijzen. Een veilige bijlageregel kan niet worden gekoppeld aan meer dan één beleid voor veilige bijlagen.

- U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige bijlagen in PowerShell die pas beschikbaar zijn in het beveiligings- & compliancecentrum nadat u het beleid hebt gemaakt:
  - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-SafeAttachmentRule).**
  - Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **New-SafeAttachmentRule).**

- Een nieuw beleid voor veilige bijlagen dat u in PowerShell maakt, is pas zichtbaar in het Beveiligings- & Compliancecentrum als u het beleid aan een veilige bijlageregel toewijst.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Stap 1: PowerShell gebruiken om een veilig bijlagebeleid te maken

Als u een beleid voor veilige bijlagen wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

In dit voorbeeld wordt een beleid voor veilige bijlagen met de naam Contoso All gemaakt met de volgende waarden:

- Blokkeer berichten die malware bevatten door documenten Safe scannen (we gebruiken de _parameter_ Actie niet en de standaardwaarde is `Block` ).
- Omleiding is ingeschakeld en berichten die malware bevatten, worden naar sec-ops@contoso.com verzonden voor analyse en onderzoek.
- Als Safe het scannen van bijlagen niet beschikbaar is of fouten ondervindt, levert u het bericht niet op (we gebruiken de parameter _ActionOnError_ niet en de standaardwaarde is `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Zie [New-SafeAttachmentPolicy (Nieuw-SafeAttachmentPolicy)](/powershell/module/exchange/new-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Stap 2: PowerShell gebruiken om een veilige bijlageregel te maken

Als u een veilige bijlageregel wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In dit voorbeeld wordt een veilige bijlageregel met de naam Contoso All gemaakt met de volgende voorwaarden:

- De regel is gekoppeld aan het beleid voor veilige bijlagen met de naam Contoso All.
- De regel is van toepassing op alle geadresseerden in het contoso.com domein.
- Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.
- De regel is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Zie [New-SafeAttachmentRule voor](/powershell/module/exchange/new-safeattachmentrule)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-safe-attachment-policies"></a>PowerShell gebruiken om beleidsregels voor veilige bijlagen weer te geven

Gebruik de volgende syntaxis als u bestaande beleidsregels voor veilige bijlagen wilt weergeven:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle beleidsregels voor veilige bijlagen weergegeven.

```PowerShell
Get-SafeAttachmentPolicy
```

Dit voorbeeld retourneert gedetailleerde informatie voor het beleid voor veilige bijlagen met de naam Contoso Executives.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Zie [Get-SafeAttachmentPolicy (Get-SafeAttachmentPolicy)](/powershell/module/exchange/get-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-safe-attachment-rules"></a>PowerShell gebruiken om regels voor veilige bijlagen weer te geven

Als u bestaande regels voor veilige bijlagen wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle regels voor veilige bijlagen weergegeven.

```PowerShell
Get-SafeAttachmentRule
```

Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

Dit voorbeeld retourneert gedetailleerde informatie voor de veilige bijlageregel met de naam Contoso Executives.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Zie [Get-SafeAttachmentRule (Get-SafeAttachmentRule)](/powershell/module/exchange/get-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>PowerShell gebruiken om beleidsregels voor veilige bijlagen te wijzigen

U kunt de naam van een beleid voor veilige bijlagen niet wijzigen in PowerShell (de cmdlet **Set-SafeAttachmentPolicy** heeft geen _naamparameter)._ Wanneer u de naam van een Safe bijlagebeleid wijzigt in het Beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de regel voor veilige _bijlagen._

Anders zijn dezelfde instellingen beschikbaar wanneer u een beleid voor veilige bijlagen maakt, zoals wordt beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) gebruiken om eerder in dit artikel een sectie voor het beleid voor veilige bijlagen te maken.

Als u een beleid voor veilige bijlagen wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-SafeAttachmentPolicy (Set-SafeAttachmentPolicy)](/powershell/module/exchange/set-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell gebruiken om regels voor veilige bijlagen te wijzigen

De enige instelling die niet beschikbaar is wanneer u een veilige bijlageregel in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor veilige bijlagen wilt in- of uitschakelen.

Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: Gebruik PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) om eerder in dit artikel een sectie met veilige bijlageregel te maken.

Als u een veilige bijlageregel wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Zie [Set-SafeAttachmentRule (Set-SafeAttachmentRule)](/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell gebruiken om regels voor veilige bijlagen in of uit te schakelen

Als u een veilige bijlageregel in PowerShell in- of uitschakelen, wordt het hele Safe-bijlagebeleid (de veilige bijlageregel en het toegewezen beleid voor veilige bijlagen) in- of uitgeschakeld.

Als u een veilige bijlageregel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de veilige bijlageregel marketingafdeling uitgeschakeld.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Zie [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule (Enable-SafeAttachmentRule en Disable-SafeAttachmentRule)](/powershell/module/exchange/disable-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>PowerShell gebruiken om de prioriteit van regels voor veilige bijlagen in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit van een veilige bijlageregel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Opmerking:** Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u de parameter _Prioriteit_ op de cmdlet **New-SafeAttachmentRule.**

Zie [Set-SafeAttachmentRule (Set-SafeAttachmentRule)](/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>PowerShell gebruiken om beleid voor veilige bijlagen te verwijderen

Wanneer u PowerShell gebruikt om een beleid voor veilige bijlagen te verwijderen, wordt de bijbehorende regel voor veilige bijlagen niet verwijderd.

Als u een beleid voor veilige bijlagen in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het beleid voor veilige bijlagen met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Zie [Remove-SafeAttachmentPolicy (Remove-SafeAttachmentPolicy)](/powershell/module/exchange/remove-safeattachmentpolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>PowerShell gebruiken om regels voor veilige bijlagen te verwijderen

Wanneer u PowerShell gebruikt om een veilige bijlageregel te verwijderen, wordt het bijbehorende beleid voor veilige bijlagen niet verwijderd.

Als u een veilige bijlageregel in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de veilige bijlageregel marketingafdeling verwijderd.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Zie [Remove-SafeAttachmentRule (Remove-SafeAttachmentRule)](/powershell/module/exchange/remove-safeattachmentrule)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u het beleid voor bijlagen hebt gemaakt, gewijzigd of Safe verwijderd, gaat u als volgt te werk:

- Ga in het & Compliancecentrum naar **ATP** voor bedreigingsbeheerbeleid \>  \> **Safe Bijlagen.** Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.** Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.

- Vervang Exchange Online PowerShell of Exchange Online Protection PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en controleer \<Name\> de instellingen:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Als u wilt controleren Safe bijlagen berichten scannen, controleert u de beschikbare Defender voor Office 365 rapporten. Zie Rapporten voor Defender voor Office 365 [en](view-reports-for-mdo.md) Explorer gebruiken in het beveiligings- [& compliancecentrum voor meer informatie.](threat-explorer.md)
