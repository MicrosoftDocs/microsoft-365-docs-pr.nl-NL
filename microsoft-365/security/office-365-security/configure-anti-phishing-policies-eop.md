---
title: Antiphishingbeleid configureren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze het anti-phishingbeleid kunnen maken, wijzigen en verwijderen dat beschikbaar is in Exchange Online Protection (EOP) organisaties met of zonder Exchange Online postvakken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ee227fe622f21d5b0f520507e1d88e2bbd0f3b31
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822308"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Antiphishingbeleid configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)

In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection(EOP) organisaties zonder Exchange Online-postvakken is er een standaard anti-phishingbeleid dat een beperkt aantal anti-spoofing-functies bevat die standaard zijn ingeschakeld. Zie [Instellingen voor adresvervalsing in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings) voor meer informatie.

Beheerders kunnen het standaard anti-phishingbeleid weergeven, bewerken en configureren (maar niet verwijderen). Voor meer granulariteit kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

Organisaties met Exchange Online postvakken kunnen anti-phishingbeleid configureren in het Microsoft 365 beveiligingscentrum of in Exchange Online PowerShell. Zelfstandige EOP-organisaties kunnen alleen gebruikmaken van het beveiligingscentrum.

Zie Anti-phishingbeleid configureren in Microsoft Office 365 Defender voor Office 365 voor meer informatie over het maken en wijzigen van het meer geavanceerde [anti-phishingbeleid](configure-atp-anti-phishing-policies.md)dat beschikbaar is in Microsoft Defender voor Office 365.

De basiselementen van een anti-phishingbeleid zijn:

- **Het anti-phish-beleid:** geeft de phishingbeveiligingen aan die u wilt in- of uitschakelen en de acties om opties toe te passen.
- **De anti-phish-regel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een anti-phish-beleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid in het beveiligingscentrum beheert:

- Wanneer u een anti-phishingbeleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.
- Wanneer u een anti-phishingbeleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de anti-phish-regel. Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.
- Wanneer u een anti-phishingbeleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.

In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Gebruik Exchange Online PowerShell voor het configureren van [anti-phishingbeleid](#use-exchange-online-powershell-to-configure-anti-phishing-policies) verderop in dit artikel voor meer informatie.

Elke organisatie heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:

- Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Als u de effectiviteit van anti-phishingbeveiliging wilt vergroten, kunt u aangepaste anti-phishingbeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligingscentrum in <https://security.microsoft.com>. Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://security.microsoft.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

  U kunt anti-phishingbeleid niet beheren in zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u anti-phishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Als u alleen-lezen toegang wilt tot anti-phishingbeleid, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De **rollengroep Alleen-weergeven voor** organisatiebeheer in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezen toegang tot de <sup>\*</sup> functie.

- Zie [EOP anti-phishingbeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)voor onze aanbevolen instellingen voor anti-phishingbeleid.

- Maximaal 30 minuten toestaan dat het bijgewerkte beleid wordt toegepast.

- Zie Bestelling en prioriteit van e-mailbeveiliging voor informatie over de toepassing van anti-phishingbeleid in de [filterpijplijn.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a>Gebruik het beveiligingscentrum om anti-phishingbeleid te maken

Als u een aangepast anti-phishingbeleid maakt in het beveiligingscentrum, worden de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd gemaakt met dezelfde naam voor beide.

1. Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.

2. Klik op **de pagina Anti-phishing** op ![ Pictogram Maken ](../../media/m365-cc-sc-create-icon.png) **maken.**

3. De wizard van het beleid wordt geopend. Configureer **deze instellingen op de** pagina Beleidsnaam:
   - **Naam**: een unieke beschrijvende naam voor het beleid.
   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Wanneer u gereed bent, klikt u op **Volgende**.

4. Zoek op de pagina **Gebruikers, groepen en domeinen** die wordt weergegeven, de interne geadresseerden op wie het beleid van toepassing is (voorwaarden voor geadresseerden):
   - **Gebruikers**: de opgegeven postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw organisatie.
   - **Groepen**: de opgegeven distributiegroepen, beveiligingsgroepen met e-mail of Microsoft 365-groepen binnen uw organisatie.
   - **Domeinen**: alle geadresseerden in de opgegeven [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) binnen uw organisatie.

   Klik in het juiste vak, begin een waarde te typen en selecteer de gewenste waarde in de resultaten. Herhaal deze stap zo vaak als nodig is. Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

   Voor gebruikers of groepen kunt u de meeste id's (naam, weergavenaam, alias, e-mailadres, accountnaam, enzovoort) gebruiken, maar de bijbehorende weergavenaam wordt weergegeven in de resultaten. Voer voor gebruikers een enkel sterretje (\*) in om alle beschikbare waarden weer te geven.

   Meerdere waarden in dezelfde voorwaarde: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

   - **Deze gebruikers, groepen en domeinen uitsluiten**: als u uitzonderingen wilt toevoegen voor de interne geadresseerden op wie het beleid van toepassing is (uitzonderingen op ontvangers), selecteert u deze optie en configureert u de uitzonderingen. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Wanneer u gereed bent, klikt u op **Volgende**.

5. Op de **pagina Phishing-&** die wordt weergegeven, gebruikt u het selectievakje Spoof **intelligence** inschakelen om spoofinformatie in of uit te schakelen. De standaardwaarde is ingeschakeld (geselecteerd) en u wordt aangeraden deze aan te laten staan. U configureert de actie voor geblokkeerde vervalste berichten op de volgende pagina.

   Schakel het selectievakje uit om spoofinformatie uit te schakelen.

   > [!NOTE]
   > U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar de Microsoft 365; u in plaats daarvan Verbeterde filtering voor verbindingslijnen inschakelen. Zie [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   Wanneer u gereed bent, klikt u op **Volgende**.

6. Configureer de volgende instellingen op de pagina **Acties** die wordt weergegeven:
   - **Als bericht wordt gedetecteerd als spoof:** Deze instelling is alleen beschikbaar als u **Spoofinformatie inschakelen** op de vorige pagina hebt geselecteerd. Selecteer een van de volgende acties in de vervolgkeuzelijst voor berichten van geblokkeerde vervalste afzenders:
     - **Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**
     - **Het bericht in quarantaine plaatsen**

   - **Veiligheidstips & indicatoren:** deze instelling is alleen beschikbaar als u **Spoof intelligence inschakelen** op de vorige pagina hebt geselecteerd:
     - **Weergeven (?)** voor niet-nautische afzenders voor spoof: Hiermee wordt een vraagteken toegevoegd aan de foto van de afzender in het  vak Van in Outlook als het bericht niet door SPF- of DKIM-controles wordt gecontroleerd en het bericht niet door DMARC of samengestelde verificatie [komt.](email-validation-and-authentication.md#composite-authentication)
     - **Tag 'via' tonen:** hiermee voegt u een via-tag (chris@contoso.com via fabrikam.com) toe aan het Van-adres als deze verschilt van het domein in de DKIM-handtekening of het **MAIL** FROM-adres.

       > [!NOTE]
       > Op dit moment is de taginstelling **'via'** tonen niet beschikbaar in alle organisaties. Als u de taginstelling **'via'** tonen niet hebt, worden het vraagteken en de via-tag beide beheerd door de instelling Tonen  **(?)** voor niet-genauteerde afzenders voor spoofinstelling in uw organisatie.

     Schakel het selectievakje in om een instelling in te stellen. Schakel het selectievakje uit om het uit te schakelen.

   Wanneer u gereed bent, klikt u op **Volgende**.

7. Controleer uw instellingen op de pagina **Controleren** die wordt weergegeven. U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen. U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.

   Wanneer u klaar bent, klikt u op **Verzenden.**

8. Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a>Het beveiligingscentrum gebruiken om anti-phishingbeleid te bekijken

1. Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.

2. Op de **pagina Anti-phishing** worden de volgende eigenschappen weergegeven in de lijst met anti-phishingbeleidsregels:

   - **Naam**
   - **Status**
   - **Prioriteit**
   - **Laatst gewijzigd**

3. Wanneer u een beleid selecteert door op de naam te klikken, worden de beleidsinstellingen weergegeven in een flyout.

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a>Gebruik het beveiligingscentrum om anti-phishingbeleid te wijzigen

1. Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.

2. Selecteer op **de pagina Anti-phishing** een beleid in de lijst door op de naam te klikken.

3. U kunt in de flyout met beleidsdetails in elke sectie de optie **Bewerken** selecteren om de instellingen in de sectie te wijzigen. Zie Het beveiligingscentrum gebruiken om [anti-phishingbeleid](#use-the-security-center-to-create-anti-phishing-policies) te maken eerder in dit artikel voor meer informatie over de instellingen.  

   Voor het standaard anti-phishingbeleid is de sectie **Gebruikers,** groepen en domeinen niet beschikbaar (het beleid is van toepassing op iedereen) en kunt u de naam van het beleid niet wijzigen.

Zie de volgende secties als u een beleid wilt in- of uitschakelen of de beleidsprioriteitsvolgorde wilt instellen.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aangepaste anti-phishingbeleidsregels in- of uitschakelen

U kunt het standaard anti-phishingbeleid niet uitschakelen.

1. Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.

2. Selecteer op **de pagina Anti-phishing** een aangepast beleid in de lijst door op de naam te klikken.

3. Boven aan de flyout met beleidsdetails die wordt weergegeven, ziet u een van de volgende waarden:
   - **Beleid uitgeschakeld**: als u het beleid wilt inschakelen, klikt u op ![Pictogram inschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Inschakelen** .
   - **Beleid ingeschakeld**: als u het beleid wilt uitschakelen, klikt u op ![Pictogram uitschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Uitschakelen**.

4. Klik in het bevestigingsvenster dat wordt weergegeven op **Inschakelen** of **Uitschakelen**.

5. Klik in de flyout met beleidsdetails op **Sluiten**.

Op de hoofdbeleidspagina wordt de waarde **Status** van het beleid weergegeven als **Ingeschakeld** of **Uitgeschakeld**.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>De prioriteit instellen van aangepast anti-phishingbeleid

Anti-phishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **Prioriteitsnummer** niet rechtstreeks wijzigen in het beveiligingscentrum). Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.

 **Opmerkingen**:

- In het beveiligingscentrum kunt u alleen de prioriteit van het anti-phishingbeleid wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).
- Anti-phishingbeleid wordt verwerkt in de volgorde waarin ze worden weergegeven (het eerste beleid heeft de **prioriteitswaarde** 0). Het standaard anti-phishingbeleid heeft de prioriteitswaarde **Laag** en u kunt deze niet wijzigen.

1. Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.

2. Selecteer op **de pagina Anti-phishing** een aangepast beleid in de lijst door op de naam te klikken.

3. Boven aan de flyout met beleidsgegevens die wordt weergegeven, ziet u **Prioriteit verhogen** of **Prioriteit verlagen** op basis van de huidige prioriteitswaarde en het aantal aangepaste beleidsregels:
   - Het anti-phishingbeleid met **prioriteitswaarde** **0** heeft alleen de **optie Prioriteit verlagen** beschikbaar.
   - Het anti-phishingbeleid met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de optie **Prioriteit verhogen** beschikbaar.
   - Als u drie of meer anti-phishingbeleidsregels hebt, hebben beleidsregels tussen  de hoogste en laagste prioriteit zowel de opties Prioriteit verhogen als Prioriteit verlagen beschikbaar. 

   Klik op het ![pictogram Prioriteit verhogen](../../media/m365-cc-sc-increase-icon.png) **Prioriteit verhogen** of ![Pictogram Prioriteit verlagen](../../media/m365-cc-sc-decrease-icon.png) **Prioriteit verlagen** om de **Prioriteitswaarde** te wijzigen.

4. Wanneer u klaar bent, klikt u in de flyout met beleidsdetails op **Sluiten**.

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a>Gebruik het beveiligingscentrum om aangepaste anti-phishingbeleidsregels te verwijderen

Wanneer u het beveiligingscentrum gebruikt om een aangepast anti-phishingbeleid te verwijderen, worden de anti-phish-regel en het bijbehorende anti-phish-beleid beide verwijderd. U kunt het standaard anti-phishingbeleid niet verwijderen.

1. Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**.

2. Selecteer een aangepast beleid in de lijst door op de naam van het beleid te klikken. Klik boven aan de flyout met beleidsdetails die wordt weergegeven, op het ![pictogram Meer acties](../../media/m365-cc-sc-more-actions-icon.png) **Meer acties** \> ![Pictogram Beleid verwijderen](../../media/m365-cc-sc-delete-icon.png) **Beleid verwijderen**.

3. Klik in het bevestigingsvenster dat wordt weergegeven op **Ja**.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Gebruik Exchange Online PowerShell om anti-phishingbeleid te configureren

Zoals eerder beschreven, bestaat een anti-phishingbeleid uit een anti-phish-beleid en een anti-phish-regel.

In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk. U beheert anti-phish-beleid met behulp van **\* de cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de **\* cmdlets -AntiPhishRule.**

- In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel waarin het beleid wordt aangegeven waar de regel op van toepassing is.
- In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.
- Wanneer u een anti-phish-beleid verwijdert uit PowerShell, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.

> [!NOTE]
> De volgende PowerShell-procedures zijn niet beschikbaar in zelfstandige EOP-organisaties met Exchange Online Protection PowerShell.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell gebruiken om anti-phishingbeleid te maken

Het maken van een anti-phishingbeleid in PowerShell is een proces in twee stappen:

1. Maak het anti-phish-beleid.
2. Maak de anti-phish-regel die het anti-phish-beleid aangeeft waar de regel op van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe anti-phish-regel maken en er een bestaand, niet-verbonden anti-phish-beleid aan toewijzen. Een anti-phish-regel kan niet worden gekoppeld aan meer dan één anti-phish-beleid.

- U kunt de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in het beveiligingscentrum nadat u het beleid hebt gemaakt:

  - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-AntiPhishRule).**
  - Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**

- Een nieuw anti-phish-beleid dat u in PowerShell maakt, is pas zichtbaar in het beveiligingscentrum als u het beleid aan een anti-phish-regel toewijst.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken

Als u een anti-phish-beleid wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

In dit voorbeeld wordt een anti-phish-beleid met de naam Onderzoek quarantaine gemaakt met de volgende instellingen:

- De beschrijving is: Het beleid van de onderzoeksafdeling.
- Wijzigt de standaardactie voor spoofing in Quarantaine.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Zie [Nieuw-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Stap 2: PowerShell gebruiken om een anti-phish-regel te maken

Als u een anti-phish-regel wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een anti-phish-regel met de naam Onderzoeksafdeling gemaakt met de volgende voorwaarden:

- De regel is gekoppeld aan het anti phish-beleid met de naam Research Quarantine.
- De regel is van toepassing op leden van de groep met de naam Onderzoeksafdeling.
- Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Zie [Nieuw-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid weer te geven

Gebruik de volgende syntaxis als u bestaande anti-phish-beleidsregels wilt weergeven:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle anti-phish-beleidsregels samen met de opgegeven eigenschappen weergegeven.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

Dit voorbeeld retourneert alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Zie [Get-AntiPhishPolicy (Get-AntiPhishPolicy)](/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels weer te geven

Als u bestaande anti-phish-regels wilt bekijken, gebruikt u de volgende syntaxis:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle anti-phish-regels samen met de opgegeven eigenschappen weergegeven.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

Dit voorbeeld retourneert alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Zie [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid te wijzigen

Naast de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u een beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit artikel een [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) te maken.

- De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (toegepast op iedereen, altijd Laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.
- U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._ Wanneer u de naam van een anti-phishingbeleid in het beveiligingscentrum wijzigt, wijzigt u alleen de naam van de anti-phish-regel. 

Als u een anti-phish-beleid wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.

Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit artikel een [anti-phish-regelsectie](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken.

Als u een anti-phish-regel wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Zie [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels in of uit te schakelen

Als u een anti-phish-regel in PowerShell in- of uitschakelen, wordt het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) in- of uitgeschakeld. U kunt het standaard anti-phishingbeleid niet in- of uitschakelen (dit beleid wordt altijd toegepast op alle geadresseerden).

Als u een anti-phish-regel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de anti-phish-regel marketingafdeling uitgeschakeld.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Zie [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and Disable-AntiPhishRule (Inschakelen-AntiPhishRule en [Disable-AntiPhishRule)](/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit van een anti-phish-regel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Opmerkingen**:

- Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-AntiPhishRule.**
- Het standaard anti-phish-beleid heeft geen bijbehorende anti-phish-regel en heeft altijd de onmodifieerbare **prioriteitswaarde Laag**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid te verwijderen

Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.

Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het anti-phish-beleid met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Zie [Remove-AntiPhishPolicy (Verwijderen-AntiPhishPolicy)](/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels te verwijderen

Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.

Als u een anti-phish-regel in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de anti-phish-regel marketingafdeling verwijderd.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Zie [Remove-AntiPhishRule (Verwijderen-AntiPhishRule)](/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u anti-phishingbeleid hebt geconfigureerd in EOP, gaat u als volgt te werk:

- Ga in het beveiligingscentrum naar **E-mail & samenwerkingsbeleid** & sectie Beleidsregels voor bedreigingsbeleid \>  \>  \>  \> **Anti-phishing**. Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.** Als u meer details wilt weergeven, selecteert u het beleid in de lijst door op de naam te klikken en de details weer te geven in de flyout die wordt weergegeven.

- Vervang Exchange Online PowerShell door de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
