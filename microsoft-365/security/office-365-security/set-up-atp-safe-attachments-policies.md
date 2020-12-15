---
title: Beleidsregels voor veilige bijlagen instellen in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Meer informatie over het definiëren van beleidsregels voor veilige bijlagen om uw organisatie tegen kwaadwillende bestanden in een e-mail te beschermen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9105e7ed9e9bc376b3d86cd846d8c1d6eae8deea
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682902"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Beleidsregels voor veilige bijlagen instellen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben. Als u een thuisgebruiker bent die op zoek bent naar informatie over het scannen van bijlagen in Outlook, raadpleegt u [geavanceerde Outlook.com-beveiliging](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Veilige bijlagen is een functie in [Microsoft Defender voor Office 365](office-365-atp.md) waarbij een virtuele omgeving wordt gebruikt voor het controleren van bijlagen in inkomende e-mailberichten nadat ze zijn gescand door [beveiliging tegen malware in Exchange Online Protection (EOP)](anti-malware-protection.md), maar voordat ze worden bezorgd voor geadresseerden. Zie voor meer informatie [veilige bijlagen in Microsoft Defender voor Office 365](atp-safe-attachments.md).

Er is geen ingebouwd of standaardbeleid voor veilige bijlagen. Als u veilig bijlagen wilt scannen van bijlagen bij e-mailberichten, moet u een of meer beleidsregels voor veilige bijlagen maken, zoals wordt beschreven in dit artikel.

U kunt beleidsregels voor veilige bijlagen in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell) configureren voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met invoegtoepassingen voor Office 365.

De basiselementen van een veilig bijlage beleid zijn:

- Met **het beleid voor veilige bijlagen**: Hiermee geeft u de acties voor onbekende detectie van malware op, of u berichten met schadelijke software wilt verzenden naar een opgegeven e-mailadres en of u berichten wilt bezorgen als het scannen van veilige bijlagen niet mogelijk is.
- Met **de veilige bijlage regel**: Hiermee geeft u de prioriteiten en de filters voor geadresseerden op (waarvoor het beleid van toepassing is).

Het verschil tussen deze twee elementen is niet duidelijk wanneer u beveiligingsmaatregelen voor veilige bijlagen beheert in de beveiligings & nalevings centrum:

- Wanneer u een beleid voor veilige bijlagen maakt, maakt u eigenlijk een veilige bijlage regel en het bijbehorende veilige bijlage beleid tegelijk met dezelfde naam voor beide.
- Wanneer u een veilig bijlage beleid wijzigt, worden de instellingen voor de naam, de prioriteit, ingeschakeld of uitgeschakeld en de filters voor geadresseerden gewijzigd in de veilige bijlage regel. Alle andere instellingen wijzigen het bijbehorende veilige bijlage beleid.
- Wanneer u een beleid voor veilige bijlagen verwijdert, worden de veilige bijlage regel en het bijbehorende veilige bijlage beleid verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie voor meer informatie de sectie [Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken voor het configureren](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) van de sectie voor het opstellen van veilige bijlagen verderop in dit artikel.

> [!NOTE]
> In het gebied algemene instellingen van instellingen voor veilige bijlagen configureert u functies die niet afhankelijk zijn van beleid voor veilige bijlagen. Zie [ATP voor SharePoint, OneDrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md) en [veilige documenten in Microsoft 365 E5](safe-docs.md)inschakelen voor instructies.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina met **veilige bijlagen** wilt gaan, gebruikt u <https://protection.office.com/safeattachmentv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:
  - Als u beleidsregels voor veilige bijlagen wilt maken, wijzigen en verwijderen, moet u lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .
  - Voor alleen-lezen toegang tot beveiligingsbeleid voor veilige bijlagen moet u lid zijn van de rollen groepen **algemene lezer** of **beveiligings lezer** .

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie [instellingen voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)voor de aanbevolen instellingen voor beleidsregels voor veilige bijlagen.

- Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor het maken van veilige bijlagen te maken

Als u een aangepast veilig bijlagebeleid maakt in de beveiligings & nalevings centrum, wordt de veilige bijlage regel en het bijbehorende veilige bijlage beleid tegelijk gemaakt met dezelfde naam voor beide.

1. Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.

2. Klik op de pagina met **veilige bijlagen** op **maken**.

3. De wizard **nieuwe beleidsregels voor veilige bijlagen** wordt geopend. Configureer de volgende instellingen op de pagina **naam van uw beleid** :

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Wanneer u klaar bent, klikt u op **volgende**.

4. Configureer de volgende instellingen op de pagina **instellingen** die wordt weergegeven:

   - **Veilige bijlagen onbekende schadelijk malware-antwoord**: Selecteer een van de volgende waarden:

     - **Uit**: meestal wordt deze waarde niet aangeraden.
     - **Monitor**
     - **Blok**: dit is de standaardwaarde en de aanbevolen waarde in de standaard en strikte [vooraf ingestelde beveiligingsbeleidsregels](preset-security-policies.md).
     - **Vervangen**
     - **Dynamische bezorging (preview-functie)**

     Deze waarden worden uitgelegd in de [beleidsinstellingen voor veilige bijlagen](atp-safe-attachments.md#safe-attachments-policy-settings).

   - **Verzend de bijlage naar het volgende e-mailadres**: voor de actiewaarden **blokkeren**, **volgen** of **vervangen**, kunt u **omleiden inschakelen** selecteren voor het verzenden van berichten met bijlagen met schadelijke software naar het opgegeven interne of externe e-mailadres voor analyse en onderzoek.

     De aanbeveling voor standaard-en strikte beleidsinstellingen is om omleiding in te schakelen. Zie [instellingen voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)voor meer informatie.

   - **De bovenstaande selectie toepassen als u wilt dat malware wordt gescand op bijlagen wanneer een fout optreedt of als de fout zich voordoet**, wordt de actie die is opgegeven door veilige bijlagen, ook wel als gevolg van **schadelijke malware** op berichten. Altijd deze optie selecteren als u **ingeschakelde omleiding** selecteert. Anders zijn er mogelijk berichten verloren.

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

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige bijlagen weer te geven

1. Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.

2. Selecteer een beleid in de lijst op de pagina **veilige bijlagen** en klik erop (niet het selectievakje inschakelen).

   De beleidsdetails worden in een uitgelichte vlucht weergegeven

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige bijlagen te wijzigen

1. Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.

2. Selecteer een beleid in de lijst op de pagina **veilige bijlagen** en klik erop (niet het selectievakje inschakelen).

3. Klik in de beleidsdetails die worden weergegeven, op **beleid bewerken**.

De beschikbare instellingen in de vlucht die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in de sectie [het beveiligings & gebruiken om de beleidsregels voor het maken van veilige bijlagen te maken](#use-the-security--compliance-center-to-create-safe-attachments-policies) .

Zie de volgende secties als u een beleid wilt in-of uitschakelen of de prioriteitsvolgorde voor beleidsregels wilt instellen.

### <a name="enable-or-disable-safe-attachments-policies"></a>Beleidsregels voor veilige bijlagen in-of uitschakelen

1. Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.

2. Let op de waarde in de kolom **status** :

   - Zet de wisselknop naar links ![Beleid uitschakelen](../../media/scc-toggle-off.png) om het beleid uit te schakelen.

   - De wisselknop naar rechts verplaatsen ![Beleid inschakelen](../../media/scc-toggle-on.png) het beleid in te schakelen.

### <a name="set-the-priority-of-safe-attachments-policies"></a>De prioriteit voor beleidsregels voor veilige bijlagen instellen

Beleidsregels voor veilige bijlagen krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwe policies zijn een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Beleidsregels voor veilige bijlagen worden weergegeven in de volgorde waarin ze worden verwerkt ( **het eerste** beleid heeft de waarde 0).

**Opmerking**: in het beveiligings & nalevings centrum kunt u de prioriteit van het beleid voor veilige bijlagen alleen wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit negeren wanneer u de veilige bijlage regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.

2. Selecteer een beleid in de lijst op de pagina **veilige bijlagen** en klik erop (niet het selectievakje inschakelen).

3. Voor de details van het beleid dat wordt weergegeven, klikt u op de knop beschikbare prioriteit.

   - Voor het beleid voor veilige bijlagen met de **prioriteits** waarde **0** is slechts de knop **prioriteit verlagen** beschikbaar.

   - Het beleid voor veilige bijlagen met de laagste **prioriteits** waarde (bijvoorbeeld **3**) is alleen beschikbaar voor de knop **prioriteit verhogen** .

   - Als u beschikt over drie of meer regels voor het veilig maken van bijlagen, hebben beleidsregels tussen de hoogste en laagste prioriteit de knoppen **prioriteit verhogen** en **prioriteit verlagen** .

4. Klik op **prioriteit verhogen** of **prioriteit verkleinen** om de **prioriteits** waarde te wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Het Beveiligingscentrum voor beveiligings & gebruiken om beleid voor veilige bijlagen te verwijderen

1. Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer.

2. Selecteer een beleid in de lijst op de pagina **veilige bijlagen** en klik erop (niet het selectievakje inschakelen).

3. Ga naar de details van het beleid dat wordt weergegeven, klik op **beleid verwijderen** en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>PowerShell van Exchange Online of zelfstandige EOP PowerShell gebruiken voor het configureren van de beleidsregels voor veilige bijlagen

Zoals hierboven beschreven, bestaat een beleid voor veilige bijlagen van een veilig bijlage beleid en een veilige bijlage regel.

In PowerShell is het verschil tussen veilig bijlage beleid en veilige bijlage regels zichtbaar. U beheert de beleidsregels voor veilige bijlagen met behulp van de **\* SafeAttachmentPolicy-** cmdlets en u beheert veilige bijlage regels met behulp van de cmdlets voor **\* SafeAttachmentRule** .

- In PowerShell maakt u eerst een veilig bijlagebeleid en vervolgens maakt u de veilige bijlage regel waarmee het beleid wordt aangegeven waarop de regel van toepassing is.
- In PowerShell wijzigt u de instellingen in het beleid voor veilige bijlagen en de regel voor veilige bijlagen afzonderlijk.
- Wanneer u een veilig bijlage beleid verwijdert uit PowerShell, wordt de bijbehorende veilige bijlage regel niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell gebruiken om beleid voor veilige bijlagen te maken

Het maken van een beleid voor veilige bijlagen in PowerShell is een procedure die bestaat uit twee stappen:

1. Maak een veilig bijlage beleid.
2. Maak de veilige bijlage regel waarmee het veilige bijlage beleid wordt opgegeven waarop de regel van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe veilige bijlage regel maken en een bestaand, niet-gekoppeld veilig bijlage beleid toewijzen. Een veilige bijlage regel kan niet worden gekoppeld aan meer dan één veilig bijlage beleid.

- U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor veilige bijlagen in PowerShell die niet beschikbaar zijn in het beveiligings & nalevings centrum voordat u het beleid hebt gemaakt:
  - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld_ `$false` in de **nieuwe SafeAttachmentRule-** cmdlet).
  - De prioriteit van het beleid instellen voor het maken van de _\<Number\>_ **nieuwe SafeAttachmentRule-** cmdlet (prioriteit).

- Een nieuw beleid voor veilige bijlagen dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een veilige regel regel toewijst.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Stap 1: PowerShell gebruiken om een veilig bijlage beleid te maken

U maakt een veilig bijlage beleid met de volgende syntaxis:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

In dit voorbeeld wordt een veilig bijlage beleid met de naam contoso gemaakt met de volgende waarden:

- Het blokkeren van berichten die malware bevatten door veilige documenten te scannen (we gebruiken de _actie_ parameter niet en de standaardwaarde is `Block` ).
- Omleiding is ingeschakeld, en berichten die schadelijke software bevatten, worden verzonden naar sec-ops@contoso.com voor analyse en onderzoek.
- Als het scannen van veilige bijlagen niet beschikbaar is of fouten ondervindt, moet u het bericht niet bezorgen (de parameter _ActionOnError_ wordt niet gebruikt en de standaardwaarde is `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Zie [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Stap 2: PowerShell gebruiken om een veilige bijlage regel te maken

Als u een veilige bijlage regel wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In dit voorbeeld wordt een veilige bijlage regel gemaakt met de naam contoso all met de volgende voorwaarden:

- De regel is gekoppeld aan het veilige bijlage beleid, genaamd contoso all.
- De regel geldt voor alle geadresseerden in het contoso.com-domein.
- Aangezien we de _prioriteits_ parameter niet gebruiken, wordt de standaardprioriteit gebruikt.
- De regel is ingeschakeld (de _ingeschakelde_ parameter wordt niet gebruikt en de standaardwaarde is `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Zie [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-view-safe-attachment-policies"></a>PowerShell gebruiken om veilige bijlage beleid weer te geven

Gebruik de volgende syntaxis om de bestaande beleidsregels voor veilige bijlagen weer te geven:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst weergegeven met alle beleidsregels voor veilige bijlagen.

```PowerShell
Get-SafeAttachmentPolicy
```

In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor het beleid voor veilige bijlagen met de naam contoso-leidinggevenden.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Zie [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-view-safe-attachment-rules"></a>PowerShell gebruiken om veilige bijlage regels weer te geven

Als u bestaande regels voor veilige bijlagen wilt bekijken, gebruikt u de volgende syntaxis:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle veilige bijlage regels geretourneerd.

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

In dit voorbeeld wordt gedetailleerde informatie geretourneerd voor de veilige bijlage regel genaamd contoso-leidinggevenden.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Zie [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>PowerShell gebruiken om een veilig bijlage beleid te wijzigen

U kunt de naam van een veilig bijlage beleid in PowerShell niet wijzigen (de cmdlet **set-SafeAttachmentPolicy** heeft geen _naam_ parameter). Wanneer u de naam van een beleid voor veilige bijlagen in het beveiligings & nalevings centrum wijzigt, kunt u alleen de naam van de veilige bijlage _regel_ wijzigen.

U kunt ook dezelfde instellingen gebruiken als u een veilig bijlage beleid maakt zoals wordt beschreven in de sectie [stap 1: PowerShell gebruiken voor het maken van een veilig bijlage](#step-1-use-powershell-to-create-a-safe-attachment-policy) gedeelte eerder in dit artikel.

Als u een veilig bijlage beleid wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Zie [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell gebruiken om veilige bijlage regels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een veilige bijlage regel wijzigt in PowerShell is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor veilige bijlagen wilt in-of uitschakelen.

Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals wordt beschreven in de sectie [stap 2: PowerShell gebruiken om een veilige bijlage regel te maken](#step-2-use-powershell-to-create-a-safe-attachment-rule) eerder in dit artikel.

Als u een veilige bijlage regel wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Zie [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell gebruiken om veilige bijlage regels in of uit te schakelen

Als u een veilige bijlage regel in-of uitschakelt in PowerShell, wordt het hele beleid voor veilige bijlagen (de veilige bijlage regel en het toegewezen beleid) uitgeschakeld.

Als u een veilige bijlage regel wilt in-of uitschakelen in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de veilige bijlage regel genaamd marketing afdeling uitgeschakeld.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Zie [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) en [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>PowerShell gebruiken om de prioriteit van veilige bijlage regels in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit wilt instellen voor een veilige bijlage regel in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Opmerking**: als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-SafeAttachmentRule** .

Zie [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>PowerShell gebruiken om een veilig bijlage beleid te verwijderen

Wanneer u PowerShell gebruikt om een veilig bijlage beleid te verwijderen, wordt de bijbehorende veilige bijlage regel niet verwijderd.

Als u een veilig bijlage beleid wilt verwijderen in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het beleid voor veilige bijlagen met de naam marketing afdeling verwijderd.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Zie [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>PowerShell gebruiken om veilige bijlage regels te verwijderen

Wanneer u PowerShell gebruikt om een veilige bijlage regel te verwijderen, wordt het bijbehorende veilige bijlage beleid niet verwijderd.

Als u een veilige bijlage regel wilt verwijderen in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de veilige bijlage regel genaamd marketing afdeling verwijderd.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Zie [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Voer een van de volgende stappen uit om te controleren of u het beleid voor veilige bijlagen hebt gemaakt, gewijzigd of verwijderd:

- Ga in het beveiligings & compliance naar  \>  \> **veilige bijlagen** voor het beleid voor risicobeheer. Controleer de lijst met beleidsregels, de **status** waarden en de waarden van de **prioriteit** . Als u meer informatie wilt bekijken, selecteert u het beleid in de lijst en bekijkt u de details in de vlucht.

- In Exchange Online PowerShell of Exchange Online Protection PowerShell vervangt u \<Name\> de naam van het beleid of de regel door de volgende opdracht uit te voeren en de instellingen te controleren:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Controleer de rapporten over de beschikbare Defender voor Office 365 om te controleren of veilige bijlagen berichten controleren. Voor meer informatie raadpleegt u [rapporten weergeven voor Defender voor Office 365](view-reports-for-atp.md) en [gebruikt u de Verkenner in het beveiligings & nalevings centrum](threat-explorer.md).
