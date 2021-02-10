---
title: Beleidsregels voor veilige bijlagen instellen in Microsoft Defender voor Office 365
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
description: Meer informatie over het definiëren van beleidsregels voor veilige bijlagen om uw organisatie te beschermen tegen schadelijke bestanden in e-mail.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 314f7fd882986c22adddd0c4570b4aa9f49a40f3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166331"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Beleid voor veilige bijlagen instellen in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Dit artikel is bedoeld voor zakelijke klanten die [Microsoft Defender voor Office 365](office-365-atp.md) hebben. Als u een thuisgebruiker bent en op zoek bent naar informatie over het scannen van bijlagen in Outlook, gaat u naar [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Veilige bijlagen is een functie in Microsoft Defender voor [Office 365](office-365-atp.md) die een virtuele omgeving gebruikt om bijlagen in binnenkomende e-mailberichten te controleren nadat ze zijn gescand met beveiliging tegen [malware in Exchange Online Protection (EOP),](anti-malware-protection.md)maar voordat deze worden bezorgd bij geadresseerden. Zie Veilige bijlagen in Microsoft Defender voor [Office 365](atp-safe-attachments.md)voor meer informatie.

Er is geen ingebouwd of standaardbeleid voor veilige bijlagen. Als u wilt dat bijlagen met veilige bijlagen worden gescand in e-mailberichten, moet u een of meer beleidsregels voor veilige bijlagen maken, zoals wordt beschreven in dit artikel.

U kunt het beleid voor veilige bijlagen configureren in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor in aanmerking komende Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken, maar met Defender voor Office 365-invoegabonnementen).

De basiselementen van een beleid met veilige bijlagen zijn:

- Het beleid voor veilige **bijlagen:** hiermee geeft u de acties op voor onbekende malwaredetecties, of berichten met malware-bijlagen moeten worden verzonden naar een opgegeven e-mailadres en of berichten moeten worden verzonden als veilige bijlagen niet kunnen worden gescand.
- **De regel voor veilige bijlagen:** hiermee geeft u de prioriteit- en geadresseerdefilters op (op wie het beleid van toepassing is).

Het verschil tussen deze twee elementen is niet duidelijk wanneer u het beleid Veilige bijlagen beheert in het & Compliancecentrum:

- Wanneer u een beleid voor veilige bijlagen maakt, maakt u tegelijkertijd een veilige bijlageregel en het bijbehorende beleid voor veilige bijlagen met dezelfde naam voor beide.
- Wanneer u een beleid voor veilige bijlagen wijzigt, worden instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en worden de filters voor geadresseerden gewijzigd. Alle andere instellingen wijzigen het bijbehorende beleid voor veilige bijlagen.
- Wanneer u een beleid voor veilige bijlagen verwijdert, worden de regels voor veilige bijlagen en het bijbehorende beleid voor veilige bijlagen verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Exchange Online PowerShell of de zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) gebruiken om beleidsregels voor veilige bijlagen verderop in dit artikel te configureren.

> [!NOTE]
> In het gebied met globale instellingen van de instellingen voor veilige bijlagen configureert u functies die niet afhankelijk zijn van het beleid voor veilige bijlagen. Zie Veilige bijlagen [in microsoft](turn-on-atp-for-spo-odb-and-teams.md) 365 E5 in microsoft [365 E5](safe-docs.md)voor instructies.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **pagina Veilige bijlagen wilt** gaan, gebruikt u <https://protection.office.com/safeattachmentv2> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet machtigingen toegewezen krijgen voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u een beleid voor veilige bijlagen wilt maken, wijzigen en  verwijderen, moet u lid zijn van  de rollengroepen  Organisatiebeheer of Beveiligingsbeheerder in het beveiligings- &-compliancecentrum en lid zijn van de rollengroep Organisatiebeheer in Exchange Online. 
  - Voor alleen-lezen toegang tot het beleid voor veilige bijlagen  moet  u lid zijn van de rollengroepen Globale lezer of Beveiligingslezer in het & Compliancecentrum.

  Zie Machtigingen in [het beveiligings-](permissions-in-the-security-and-compliance-center.md) en & en [machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie Instellingen voor veilige bijlagen voor de aanbevolen instellingen voor het beleid [voor veilige bijlagen.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

- Het kan 30 minuten duren voordat een nieuw of bijgewerkt beleid wordt toegepast.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Het beveiligings- & gebruiken om beleid voor veilige bijlagen te maken

Als u een aangepast beleid voor veilige bijlagen maakt in het beveiligings- & Compliancecentrum, worden de regels voor veilige bijlagen en het bijbehorende beleid voor veilige bijlagen op hetzelfde moment met dezelfde naam voor beide gemaakt.

1. Ga in het & compliancecentrum  naar Veilige bijlagen van ATP voor \>  \> **risicobeheerbeleid.**

2. Klik op **de pagina Veilige bijlagen** op **Maken.**

3. De **wizard Nieuwe veilige bijlagen wordt** geopend. Configureer **de volgende instellingen op** de pagina Uw beleid een naam geven:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Klik op Volgende wanneer u klaar **bent.**

4. Configureer **de volgende** instellingen op de pagina Instellingen die wordt weergegeven:

   - **Safe Attachments unknown malware response**: Select one of the following values:

     - **Uit:** deze waarde wordt meestal niet aanbevolen.
     - **Monitor**
     - **Blokkeren:** dit is de standaardwaarde en de aanbevolen waarde in standaard- en [strikt vooraf ingestelde beveiligingsbeleidsregels.](preset-security-policies.md)
     - **Vervangen**
     - **Dynamische bezorging (preview-functie)**

     Deze waarden worden uitgelegd in [de beleidsinstellingen voor veilige bijlagen.](atp-safe-attachments.md#safe-attachments-policy-settings)

   - Verstuur de bijlage naar het volgende e-mailadres: voor de actiewaarden  **Blokkeren,** Controleren of Vervangen, kunt u Omleiding inschakelen selecteren om berichten met malwarebijlagen te verzenden naar het opgegeven interne of externe e-mailadres voor analyse en onderzoek.  

     Het wordt aanbevolen voor standaard- en striktbeleidsinstellingen om omleiding in teschakelen. Zie instellingen voor [veilige bijlagen voor meer informatie.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)

   - **Pas de bovenstaande** selectie toe als malware wordt gescand op bijlagen in de tijd of als er een fout optreedt: De actie die wordt opgegeven door Safe **Attachments onbekende malwarereactie** wordt uitgevoerd op berichten, zelfs als het scannen van veilige bijlagen niet kan worden voltooid. Als u deze optie hebt geselecteerd, selecteert u altijd **Enabled redirect.** Anders kunnen berichten verloren gaan.

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

   Als u uitzonderingen wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als.** De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Klik op Volgende wanneer u klaar **bent.**

6. Controleer de **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven. U kunt bij **elke** instelling op Bewerken klikken om deze te wijzigen.

   Klik op Voltooien wanneer u **klaar bent.**

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige bijlagen weer te geven

1. Ga in het & compliancecentrum  naar Veilige bijlagen van ATP voor \>  \> **risicobeheerbeleid.**

2. Selecteer op **de pagina Veilige bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).

   De beleidsdetails worden in een fly-out weergegeven

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Het beveiligings- & compliancecentrum gebruiken om het beleid voor veilige bijlagen te wijzigen

1. Ga in het & compliancecentrum  naar Veilige bijlagen van ATP voor \>  \> **risicobeheerbeleid.**

2. Selecteer op **de pagina Veilige bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in het fly-out met beleidsdetails op **Beleid bewerken.**

De beschikbare instellingen in de fly out die worden weergegeven, zijn identiek aan de instellingen die worden beschreven in het [beveiligings- & Compliancecentrum](#use-the-security--compliance-center-to-create-safe-attachments-policies) gebruiken om beleidsregels voor veilige bijlagen te maken.

Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteit wilt instellen.

### <a name="enable-or-disable-safe-attachments-policies"></a>Beleid voor veilige bijlagen in- of uitschakelen

1. Ga in het & compliancecentrum  naar Veilige bijlagen van ATP voor \>  \> **risicobeheerbeleid.**

2. U ziet de waarde in de **kolom Status:**

   - De schakelknop naar links verplaatsen ![Beleid uitschakelen](../../media/scc-toggle-off.png) om het beleid uit te schakelen.

   - De schakelknop naar rechts verplaatsen ![Beleid in-/uit](../../media/scc-toggle-on.png) om het beleid in teschakelen.

### <a name="set-the-priority-of-safe-attachments-policies"></a>De prioriteit van beleidsregels voor veilige bijlagen instellen

Het beleid voor veilige bijlagen krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin het beleid is gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Beleidsregels voor veilige bijlagen worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid **heeft** de prioriteitswaarde 0).

**Opmerking:** in het & compliancecentrum kunt u de prioriteit van het beleid voor veilige bijlagen alleen wijzigen nadat u deze hebt gemaakt. In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de veilige bijlageregel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het & compliancecentrum  naar Veilige bijlagen van ATP voor \>  \> **risicobeheerbeleid.**

2. Selecteer op **de pagina Veilige bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. In de beleidsdetails die worden weergegeven, klikt u op de beschikbare prioriteitknop.

   - Voor het beleid veilige bijlagen met **prioriteitwaarde** **0** is alleen de knop Prioriteit **verlagen** beschikbaar.

   - In het beleid Veilige bijlagen met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** is alleen de knop Prioriteit **verhogen** beschikbaar.

   - Als u drie of meer beleidsregels voor veilige bijlagen hebt,  zijn voor beleid tussen de hoogste en laagste prioriteit de knoppen Hogere prioriteit en Prioriteit **verlagen** beschikbaar.

4. Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Het beveiligings- & compliancecentrum gebruiken om beleidsregels voor veilige bijlagen te verwijderen

1. Ga in het & compliancecentrum  naar Veilige bijlagen van ATP voor \>  \> **risicobeheerbeleid.**

2. Selecteer op **de pagina Veilige bijlagen** een beleid in de lijst en klik erop (schakel het selectievakje niet in).

3. Klik in het weergegeven beleidsdetails op Beleid verwijderen en klik vervolgens op **Ja** in het dialoogvenster met de waarschuwing dat wordt weergegeven. 

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om beleidsregels voor veilige bijlagen te configureren

Zoals eerder is beschreven, bestaat een beleid voor veilige bijlagen uit een beleid voor veilige bijlagen en een veilige bijlageregel.

In PowerShell is het verschil tussen een beleid voor veilige bijlagen en regels voor veilige bijlagen duidelijk. U beheert beleid voor veilige bijlagen met behulp van de cmdlets **\* -SafeAttachmentPolicy** en u beheert regels voor veilige bijlagen met behulp van de cmdlets **\* -SafeAttachmentRule.**

- In PowerShell maakt u eerst het beleid voor veilige bijlagen en maakt u vervolgens de regel voor veilige bijlagen die het beleid aangeeft dat met de regel van toepassing is.
- In PowerShell wijzigt u de instellingen in het beleid voor veilige bijlagen en de regel voor veilige bijlagen afzonderlijk.
- Wanneer u een beleid voor veilige bijlagen uit PowerShell verwijdert, wordt de bijbehorende regel voor veilige bijlagen niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>PowerShell gebruiken om beleidsregels voor veilige bijlagen te maken

Het maken van een beleid voor veilige bijlagen in PowerShell bestaat uit twee stappen:

1. Maak het beleid voor veilige bijlagen.
2. Maak de regel voor veilige bijlagen die het beleid voor veilige bijlagen aangeeft waar de regel op van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe regel voor veilige bijlagen maken en er een bestaand, niet-verbonden beleid voor veilige bijlagen aan toewijzen. Een veilige bijlageregel kan niet worden gekoppeld aan meer dan één beleid voor veilige bijlagen.

- U kunt de volgende instellingen configureren voor nieuw beleid voor veilige bijlagen in PowerShell die pas beschikbaar zijn in het beveiligings- & compliancecentrum nadat u het beleid hebt gemaakt:
  - Het nieuwe beleid maken dat is uitgeschakeld _(ingeschakeld_ `$false` op de cmdlet **New-SafeAttachmentRule).**
  - De prioriteit van het beleid instellen tijdens het maken _(prioriteit)_ _\<Number\>_ van de cmdlet **New-SafeAttachmentRule).**

- Een nieuw beleid voor veilige bijlagen dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum wanneer u het beleid toewijst aan een regel voor veilige bijlagen.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Stap 1: PowerShell gebruiken om een veilig bijlagebeleid te maken

Gebruik de volgende syntaxis om een veilig bijlagebeleid te maken:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

In dit voorbeeld wordt een beleid voor veilige bijlagen met de naam Contoso All gemaakt met de volgende waarden:

- Berichten blokkeren die malware bevatten door veilige documenten te scannen (de parameter _Actie_ wordt niet gebruikt en de standaardwaarde `Block` is).
- Omleiding is ingeschakeld en berichten die malware bevatten, worden naar het sec-ops@contoso.com voor analyse en onderzoek.
- Als scannen van veilige bijlagen niet beschikbaar is of er fouten optreden, bezorg het bericht dan niet (de parameter _ActionOnError_ wordt niet gebruikt en de standaardwaarde `$true` is).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Zie [New-SafeAttachmentPolicy voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)syntaxis- en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Stap 2: PowerShell gebruiken om een veilige bijlageregel te maken

Gebruik de volgende syntaxis om een veilige bijlageregel te maken:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In dit voorbeeld wordt een veilige bijlageregel gemaakt met de naam Contoso Alles met de volgende voorwaarden:

- De regel is gekoppeld aan het beleid voor veilige bijlagen met de naam Contoso All.
- De regel is van toepassing op alle geadresseerden in contoso.com domein.
- Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.
- De regel is ingeschakeld (de parameter _Enabled_ wordt niet gebruikt en de standaardwaarde `$true` is).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Zie [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-safe-attachment-policies"></a>PowerShell gebruiken om beleidsregels voor veilige bijlagen weer te geven

Gebruik de volgende syntaxis als u een bestaand beleid voor veilige bijlagen wilt weergeven:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst van alle beleidsregels voor veilige bijlagen weergegeven.

```PowerShell
Get-SafeAttachmentPolicy
```

In dit voorbeeld worden gedetailleerde gegevens gegeven over het beleid voor veilige bijlagen, genaamd Contoso-leidinggevenden.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Zie [Get-SafeAttachmentPolicy voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)

### <a name="use-powershell-to-view-safe-attachment-rules"></a>PowerShell gebruiken om regels voor veilige bijlagen weer te geven

Gebruik de volgende syntaxis als u bestaande regels voor veilige bijlagen wilt weergeven:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst van alle regels voor veilige bijlagen weergegeven.

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

In dit voorbeeld wordt gedetailleerde informatie gegeven over de regel voor veilige bijlagen met de naam Contoso Leidinggevenden.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Zie [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>PowerShell gebruiken om beleidsregels voor veilige bijlagen te wijzigen

U kunt de naam van een beleid voor veilige bijlagen niet wijzigen in PowerShell (de cmdlet **Set-SafeAttachmentPolicy** heeft geen _naamparameter)._ Wanneer u de naam van een beleid voor veilige bijlagen wijzigt in het beveiligings- & compliancecentrum, wijzigt u alleen de naam van de regel voor veilige _bijlagen._

Anders zijn dezelfde instellingen beschikbaar wanneer u een veilig bijlagebeleid maakt, zoals wordt beschreven in stap [1: Gebruik PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) om een sectie voor het veilige bijlagebeleid te maken eerder in dit artikel.

Gebruik de volgende syntaxis om een beleid voor veilige bijlagen te wijzigen:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-SafeAttachmentPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>PowerShell gebruiken om regels voor veilige bijlagen te wijzigen

De enige instelling die niet beschikbaar is wanneer u een regel voor veilige bijlagen wijzigt in PowerShell, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor veilige bijlagen wilt in- of uitschakelen.

Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt, zoals wordt beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) gebruiken om een sectie met een veilige bijlageregel eerder in dit artikel te maken.

Gebruik de volgende syntaxis om een veilige bijlageregel te wijzigen:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Zie [Set-SafeAttachmentRule voor](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>PowerShell gebruiken om regels voor veilige bijlagen in of uit te schakelen

Als u een regel voor veilige bijlagen in PowerShell in- of uit schakelen, wordt het hele beleid voor veilige bijlagen (de regel voor veilige bijlagen en het toegewezen beleid voor veilige bijlagen) in- of uitgeschakeld.

Gebruik de volgende syntaxis om een veilige bijlageregel in PowerShell in of uit te schakelen:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de regel voor veilige bijlagen met de naam Marketingafdeling uitgeschakeld.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Zie [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) en [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>PowerShell gebruiken om de prioriteit van regels voor veilige bijlagen in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Gebruik de volgende syntaxis om de prioriteit van een regel voor veilige bijlagen in PowerShell in te stellen:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Opmerking:** als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-SafeAttachmentRule.**

Zie [Set-SafeAttachmentRule voor](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>PowerShell gebruiken om beleidsregels voor veilige bijlagen te verwijderen

Wanneer u PowerShell gebruikt om een beleid voor veilige bijlagen te verwijderen, wordt de bijbehorende regel voor veilige bijlagen niet verwijderd.

Gebruik de volgende syntaxis om een beleid voor veilige bijlagen in PowerShell te verwijderen:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het beleid voor veilige bijlagen met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Zie [Remove-SafeAttachmentPolicy voor gedetailleerde](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)syntaxis- en parameterinformatie.

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>PowerShell gebruiken om regels voor veilige bijlagen te verwijderen

Wanneer u PowerShell gebruikt om een veilige bijlageregel te verwijderen, wordt het bijbehorende beleid voor veilige bijlagen niet verwijderd.

Gebruik de volgende syntaxis om een veilige bijlageregel in PowerShell te verwijderen:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de regel voor veilige bijlagen met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Zie [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga op een van de volgende stappen te werk om te controleren of u een beleid voor veilige bijlagen hebt gemaakt, gewijzigd of verwijderd:

- Ga in het & compliancecentrum  naar Veilige bijlagen van ATP voor \>  \> **risicobeheerbeleid.** Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.** Als u meer details wilt weergeven, selecteert u het beleid in de lijst en bekijkt u de details in de fly-out.

- Vervang in Exchange Online PowerShell of Exchange Online Protection PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Als u wilt controleren of veilige bijlagen berichten scannen, controleert u de beschikbare Defender voor Office 365-rapporten. Zie Rapporten voor Defender voor [Office 365](view-reports-for-atp.md) en Verkenner weergeven in het beveiligings- & [compliancecentrum voor](threat-explorer.md)meer informatie.
