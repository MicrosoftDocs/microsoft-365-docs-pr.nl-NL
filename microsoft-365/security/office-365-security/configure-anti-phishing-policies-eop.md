---
title: Anti-phishingbeleid configureren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u het anti-phishingbeleid maakt, wijzigt en verwijdert dat beschikbaar is in EOP-organisaties (Exchange Online Protection) met of zonder Exchange Online-postvakken.
ms.openlocfilehash: b6b95515ad44a65dbdd8a7516d8e6c8b2a386450
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726783"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Anti-phishingbeleid configureren in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, is er een standaard antiphishingbeleid dat een beperkt aantal anti-spoofingfuncties bevat die standaard zijn ingeschakeld. Zie [Spoofinstellingen in het antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

Beheerders kunnen het standaard antiphishingbeleid weergeven, bewerken en configureren (maar niet verwijderen). Voor meer granulariteit u ook aangepaste antiphishingbeleid maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

Organisaties met Exchange Online-postvakken kunnen antiphishingbeleid configureren in het Security & Compliance Center of in Exchange Online PowerShell. Zelfstandige EOP-organisaties kunnen alleen het Security & Compliance Center gebruiken.

Zie ATP-antiphishingbeleid configureren voor informatie over het maken en wijzigen van het geavanceerdere [ATP-antiphishingbeleid](configure-atp-anti-phishing-policies.md)dat beschikbaar is in Office 365 Advanced Threat Protection (Office 365 ATP).

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>Anti-phishingbeleid in het Security & Compliance Center vs PowerShell

De basiselementen van een anti-phishing beleid zijn:

- **Het anti-phish-beleid**: Hiermee geeft u de bescherming tegen phishing op om in te schakelen of uit te schakelen en de acties om opties toe te passen.

- **De anti-phish regel**: Hiermee geeft u de prioriteit en ontvanger filters (die het beleid van toepassing is op) voor een anti-phish beleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het Security & Compliance Center:

- Wanneer u een anti-phishingbeleid maakt in het Security & Compliance Center, maakt u eigenlijk een anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd met dezelfde naam voor beide.

- Wanneer u een antiphishingbeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld, en ontvangersfilters de anti-phishregel. Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.

- Wanneer u een anti-phishingbeleid verwijdert uit het Security & Compliance Center, worden de anti-phishregel en het bijbehorende anti-phish-beleid verwijderd.

In Exchange Online PowerShell is het verschil tussen anti-phish beleid en anti-phish regels duidelijk. Je beheert anti-phish beleid met behulp van de ** \* -AntiPhishPolicy** cmdlets, en je beheert anti-phish regels met behulp van de ** \* -AntiPhishRule** cmdlets.

- In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel die het beleid identificeert waarop de regel van toepassing is.

- In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.

### <a name="default-atp-anti-phishing-policy"></a>Standaard ATP-antiphishingbeleid

Elke organisatie heeft een ingebouwd antiphishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:

- Het beleid met de naam Office365 AntiPhish Default wordt toegepast op alle ontvangers in de organisatie, ook al is er geen anti-phish regel (geadresseerdefilters) gekoppeld aan het beleid.

- Het beleid met de naam Office365 AntiPhish Default heeft de aangepaste **prioriteitswaarde Laagste** die u niet wijzigen (het beleid wordt altijd als laatste toegepast). Alle aangepaste beleidsregels die u maakt, hebben altijd een hogere prioriteit dan het beleid met de naam Office365 AntiPhish Default.

- Het beleid met de naam Office365 AntiPhish Default is het standaardbeleid (de eigenschap **IsDefault** heeft de `True` waarde) en u het standaardbeleid niet verwijderen.

Om de effectiviteit van anti-phishing-bescherming te vergroten, u aangepaste anti-phishing-beleid met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **anti-phishingpagina** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

  U het beleid voor phishing niet beheren in standalone EOP PowerShell.

- U moet machtigingen krijgen voordat u de procedures in dit onderwerp uitvoeren:

  - Als u antiphishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van een van de volgende rolgroepen:

    - **Organisatiebeheer** of **beveiligingsbeheerder** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **hygiënebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

  - Voor alleen-lezen toegang tot antiphishingbeleid moet u lid zijn van een van de volgende rolgroepen:

    - **Security Reader** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-weergeven organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Om antispambeleid in standalone EOP te kunnen maken en wijzigen, moet u iets doen waarvoor _hydratatie_ voor uw tenant vereist is. In het Exchange-beheercentrum (EAC) u bijvoorbeeld naar het tabblad **Machtigingen** gaan, een bestaande rolgroep selecteren, **op** ![ pictogram Bewerken ](../../media/ITPro-EAC-EditIcon.png) klikken en een rol verwijderen (die u uiteindelijk weer toevoegt). Als uw tenant nooit is gehydrateerd, krijgt u een dialoogvenster met de naam **Organisatie-instellingen bijwerken** met een voortgangsbalk die moet worden voltooid. Zie de cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (die niet beschikbaar is in standalone EOP PowerShell of in het Security & Compliance Center) voor meer informatie over hydratatie.

- Zie [EOP-standaardbeleidsinstellingen voor antiphishing voor](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)onze aanbevolen instellingen voor antiphishingbeleid.

- Sta maximaal 30 minuten toe om het bijgewerkte beleid toe te passen.

- Zie [Volgorde en voorrang van e-mailbeveiliging](how-policies-and-protections-are-combined.md)voor informatie over waar antiphishingbeleid wordt toegepast in de filterpijplijn.

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Gebruik het Security & Compliance Center om antiphishingbeleid te maken

Als u een aangepast antiphishingbeleid maakt in het Security & Compliance Center, worden tegelijkertijd de anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide gemaakt.

Wanneer u een antiphishingbeleid maakt, u alleen de beleidsnaam, de beschrijving en het ontvangerfilter opgeven waarop wordt aangegeven op wie het beleid van toepassing is. Nadat u het beleid hebt gemaakt, u het beleid wijzigen om de standaardinstellingen voor antiphishing te wijzigen of te bekijken.

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Klik op de pagina **Anti-phishing** op **Maken**.

3. De wizard Een nieuw beleid maken met **een ander beleid maken** wordt geopend. Configureer op de pagina **Naam van uw beleid** de volgende instellingen:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Klik op **Volgende**als u klaar bent.

4. Identificeer **op** de pagina Toegepast op die wordt weergegeven de interne ontvangers waarop het beleid van toepassing is.

   U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

   Klik **op Een voorwaarde toevoegen**. Selecteer in de vervolgkeuzelijst die wordt weergegeven een voorwaarde onder **Toegepast als**:

   - **De ontvanger is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactpersonen in uw organisatie op.
   - **De ontvanger is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op.
   - **Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.

   Nadat u de voorwaarde hebt geselecteerd, wordt een overeenkomstige vervolgkeuzelijst weergegeven met **een van deze** opties.

   - Klik in het vak en blader door de lijst met waarden die u wilt selecteren.
   - Klik in het vak en begin met typen om de lijst te filteren en een waarde te selecteren.
   - Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.
   - Als u afzonderlijke vermeldingen wilt verwijderen, **klikt** u ![ op pictogram Verwijderen verwijderen op de ](../../media/scc-remove-icon.png) waarde.
   - Als u de hele **Remove** voorwaarde wilt verwijderen, klikt u ![ op pictogram Verwijderen op de ](../../media/scc-remove-icon.png) voorwaarde verwijderen.

   Als u een aanvullende voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.

   Als u uitzonderingen wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Klik op **Volgende**als u klaar bent.

5. Controleer **op** de pagina Uw instellingen die wordt weergegeven de instellingen controleren. U op Elke instelling op **Bewerken** klikken om deze te wijzigen.

   Klik op **Dit beleid maken**als u klaar bent.

6. Klik op **OK** in het bevestigingsdialoogvenster dat wordt weergegeven.

Nadat u het antiphishingbeleid hebt gemaakt met deze algemene beleidsinstellingen, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Gebruik het Security & Compliance Center om het antiphishingbeleid te wijzigen

Gebruik de volgende procedures om het antiphishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of een bestaand beleid dat u al hebt aangepast.

1. Als u er nog niet bent, opent u het Security & Compliance Center en gaat u naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen. Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.

3. De flyout **van uw beleid \<name\> bewerken** wordt weergegeven. Als u op **Bewerken** in een sectie klikt, krijgt u toegang tot de instellingen in die sectie.

   - De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u de secties in willekeurige volgorde selecteren en wijzigen).

   - Nadat u in een sectie op Bewerken hebt **geklikt,** worden de beschikbare instellingen weergegeven in een wizard-indeling, maar u in willekeurige volgorde binnen de pagina's springen en op **Opslaan** op een pagina klikken (of pictogram **Annuleren** of **Sluiten sluiten** om terug te keren naar de pagina Uw beleid ![ ](../../media/scc-remove-icon.png) ** \<name\> bewerken** (u hoeft de laatste pagina van de wizard niet te bezoeken om op te slaan of te vertrekken).

4. **Beleidsinstelling**: klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u [het beleid](#use-the-security--compliance-center-to-create-anti-phishing-policies) in de vorige sectie maakte:

   - **Naam**
   - **Beschrijving**
   - **Toegepast op**
   - **Uw instellingen bekijken**

   Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.

5. **Spoof**: klik op **Bewerken** om spoofinformatie in of uit te schakelen, de identificatie van niet-geverifieerde afzenders in Of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders. Zie [Spoofinstellingen in het antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

   Houd er rekening mee dat dezelfde instellingen ook beschikbaar zijn in het ATP-anti-phishingbeleid.

   - **Instellingen voor spoofingfilters:** de standaardwaarde is **ingeschakeld**en we raden u aan deze aan te laten. Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit**. Zie [Spoofintelligentie configureren in EOP](learn-about-spoof-intelligence.md)voor meer informatie.

     > [!NOTE]
     > U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar Microsoft 365 wijst; u in plaats daarvan Uitgebreide filtering voor connectoren inschakelt. Zie Uitgebreide [filtering voor connectoren in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor instructies.

   - **Functie niet-geverifieerde afzender inschakelen:** de standaardwaarde is **ingeschakeld.** Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit**.

   - **Acties**: Geef de actie op die moet worden uitgevoerd op berichten die niet intelligentie hebben:

     **Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen:**

     - **Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**
     - **Quarantaine het bericht**

   - **Uw instellingen bekijken:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.

     - U in elke sectie op **Bewerken** klikken om terug te springen naar de desbetreffende pagina.
     - U de volgende instellingen rechtstreeks **in-** of **uitschakelen** op deze pagina:

       - **Bescherming tegenpoofing inschakelen**
       - **Functie niet-geverifieerde afzender inschakelen**

   Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.

6. Terug op de pagina **Uw beleid \<Name\> bewerken,** uw instellingen controleren en vervolgens op **Sluiten**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Gebruik het Security & Compliance Center om het standaard anti-phishingbeleid te wijzigen

Het standaardbeleid voor antiphishing wordt Office365 AntiPhish Default genoemd en wordt niet weergegeven in de lijst met beleidsregels. Als u het standaardbeleid voor antiphishing wilt wijzigen, voert u de volgende stappen uit:

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Klik op de pagina **Antiphishing** op **Standaardbeleid**.

3. De pagina **Office365 AntiPhish Default-standaard** van het beleid bewerken, wordt weergegeven. De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **Imitatie**
   - **Spoof**
   - **Geavanceerde instellingen**

   De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:

   - U de sectie **Beleidsinstelling** en waarden zien, maar er is geen koppeling **bewerken,** dus u de instellingen niet wijzigen (beleidsnaam, beschrijving en op wie het beleid van toepassing is (het is van toepassing op alle ontvangers)).
   - U het standaardbeleid niet verwijderen.
   - U de prioriteit van het standaardbeleid niet wijzigen (het wordt altijd als laatste toegepast).

4. Bekijk op de pagina **Office365 AntiPhish Default bewerken** de instellingen en klik op **Sluiten**.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aangepast antiphishingbeleid in- of uitschakelen

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Let op de waarde in de kolom **Status:**

   - Schuif de schakel naar **Uit** om het beleid uit te schakelen.

   - Schuif de schakelaar **naar Aan** om het beleid in te schakelen.

U het standaardbeleid voor antiphishing niet uitschakelen.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>De prioriteit van aangepast antiphishingbeleid instellen

Antiphishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.

Aangepaste anti-phishingbeleid wordt weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0). Het standaardbeleid voor antiphishing met de naam Office365 AntiPhish Default heeft de aangepaste **prioriteitswaarde Laagste**en u deze niet wijzigen.

 **Opmerking:** In het Security & Compliance Center u de prioriteit van het antiphishingbeleid alleen wijzigen nadat u het hebt gemaakt. In PowerShell u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).

Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u het **prioriteitsnummer** niet direct wijzigen in het Security & Compliance Center). Het wijzigen van de prioriteit van een beleid heeft alleen zin als u meerdere beleidsregels hebt.

1. Ga in het Security & Compliance **Threat management** Center naar \> **Policy** \> **AtP-antiphishing**van threat management.

2. Selecteer het beleid dat u wilt wijzigen. Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.

3. De flyout **van uw beleid \<name\> bewerken** wordt weergegeven.

   - Het aangepaste anti-phishingbeleid met de **prioriteitswaarde** **0** heeft alleen de knop **Prioriteit verlagen** beschikbaar.

   - Het aangepaste anti-phishingbeleid met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.

   - Als u drie of meer aangepaste antiphishingbeleid hebt, hebben beleidsregels tussen de hoogste en laagste prioriteitswaarden zowel de knoppen **Prioriteit Verhogen** als **Prioriteitsknoppen verlagen** beschikbaar.

4. Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde** te wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Gebruik het Security & Compliance Center om antiphishingbeleid te bekijken

1. In het Security & Compliance Center en ga naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Een van de volgende stappen uitvoeren:

   - Selecteer een aangepast antiphishingbeleid dat u wilt weergeven. Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.

   - Klik **op Standaardbeleid** om het standaardbeleid voor phishing weer te geven.

3. De flyout **van uw beleid \<name\> bewerken** wordt weergegeven, waar u de instellingen en waarden bekijken.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Gebruik het Security & Compliance Center om antiphishingbeleid te verwijderen

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Selecteer het beleid dat u wilt verwijderen. Als het al is geselecteerd, schakelt u de selectie uit en selecteert u het opnieuw.

3. Klik in de flyout **beleid \<name\> bewerken** die wordt weergegeven op **Beleid verwijderen**en klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Exchange Online PowerShell gebruiken om antiphishingbeleid te configureren

De volgende procedures zijn niet beschikbaar in zelfstandige EOP-organisaties.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell gebruiken om antiphishingbeleid te maken

Het maken van een anti-phishing beleid in PowerShell is een proces in twee stappen:

1. Maak het anti-phish beleid.

2. Maak de anti-phish regel die het anti-phish beleid aangeeft waarop de regel van toepassing is.

 **Opmerkingen**:

- U een nieuwe anti-phish regel maken en er een bestaand, niet-gekoppeld anti-phish beleid aan toewijzen. Een anti-phish regel kan niet worden geassocieerd met meer dan een anti-phish beleid.

- U de volgende instellingen voor nieuw antifromancebeleid configureren in PowerShell die pas beschikbaar zijn in het Security & Compliance Center nadat u het beleid hebt gemaakt:

  - Maak het nieuwe beleid als uitgeschakeld (_Ingeschakeld_ `$false` op de cmdlet **Nieuw-AntiPhishRule).**

  - Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**

- Een nieuw anti-phish-beleid dat u maakt in PowerShell, is niet zichtbaar in het Security & Compliance Center totdat u het beleid toewijst aan een anti-phish regel.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken

Als u een anti-phish-beleid wilt maken, gebruikt u deze syntaxis:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

In dit voorbeeld wordt een anti-phish-beleid met de naam Research Quarantine gemaakt met de volgende instellingen:

- Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld niet_ en de standaardwaarde is `$true` ).
- De beschrijving is: Onderzoek afdelingsbeleid.
- Hiermee wijzigt u de standaardactie voor spoofing in Quarantaine.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Zie [Nieuw-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)gedetailleerde syntaxis- en parametergegevens .

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Stap 2: PowerShell gebruiken om een anti-phish-regel te maken

Als u een anti-phish-regel wilt maken, gebruikt u deze syntaxis:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een anti-phish-regel met de naam Research Department gemaakt met de volgende voorwaarden:

- De regel is gekoppeld aan het anti-phish beleid genaamd Research Quarantine.
- De regel is van toepassing op leden van de groep met de naam Research Department.
- Omdat we de parameter _Prioriteit_ niet gebruiken, wordt de standaardprioriteit gebruikt.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Zie [Nieuw-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)gedetailleerde syntaxis- en parametergegevens .

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid te bekijken

Als u bestaande anti-phish-beleid wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst geretourneerd met alle anti-phish-beleidsregels, samen met de opgegeven eigenschappen.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor het anti-phish-beleid met de naam Executives.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie .

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell gebruiken om anti-phish regels te bekijken

Als u bestaande anti-phishregels wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst van alle anti-phishregels samen met de opgegeven eigenschappen geretourneerd.

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

In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor de anti-phish-regel met de naam Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie .

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid te wijzigen

Anders dan de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit onderwerp [een anti-phish beleidssectie te maken.](#step-1-use-powershell-to-create-an-anti-phish-policy)

- De _Schakelaar Fout maken_ die het opgegeven beleid verandert in het standaardbeleid (toegepast op iedereen, altijd **laagste** prioriteit en u deze niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.

- U de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen parameter _Name)._ Wanneer u de naam van een anti-phishingbeleid wijzigt in het Security & Compliance _rule_Center, wijzigt u alleen de anti-phish-regel .

Als u een anti-phish-beleid wilt wijzigen, gebruikt u deze syntaxis:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)gedetailleerde syntaxis- en parametergegevens .

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell gebruiken om anti-phish regels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een anti-phish regel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken. Zie de volgende sectie om bestaande anti-phishregels in of uit te schakelen.

Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phish-regel wijzigt in PowerShell. Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een anti-phish regelsectie te maken.](#step-2-use-powershell-to-create-an-anti-phish-rule)

Als u een anti-phishregel wilt wijzigen, gebruikt u deze syntaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Zie [Set-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)gedetailleerde syntaxis- en parametergegevens .

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell gebruiken om anti-phishregels in te schakelen of uit te schakelen

Het in- of uitschakelen van een anti-phish-regel in PowerShell maakt het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) mogelijk of uitgeschakeld. U het standaardbeleid voor antiphishing niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).

Als u een anti-phishregel in PowerShell wilt in- of uitschakelen, gebruikt u deze syntaxis:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de anti-phish-regel met de naam Marketing Department uitgeschakeld.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) en [AntiPhishRule uitschakelen](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)voor gedetailleerde syntaxis- en parametergegevens .

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell gebruiken om de prioriteit van anti-phish regels in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit van een anti-phishregel wilt instellen in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Opmerkingen**:

- Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **Nieuw-AntiPhishRule.**

- De standaard anti-phish beleid heeft geen overeenkomstige anti-phish regel, en het heeft altijd de onmodifiable **prioriteitswaarde Laagste**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid te verwijderen

Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phishregel niet verwijderd.

Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u deze syntaxis:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het anti-phish-beleid met de naam Marketing Department verwijderd.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Zie [Remove-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)gedetailleerde syntaxis- en parametergegevens .

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell gebruiken om anti-phish regels te verwijderen

Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.

Als u een anti-phishregel in PowerShell wilt verwijderen, gebruikt u deze syntaxis:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de anti-phish-regel met de naam Marketing Department verwijderd.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Zie [Remove-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)gedetailleerde syntaxis- en parametergegevens .

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Als u wilt controleren of u het ATP-antiphishingbeleid hebt geconfigureerd, voert u een van de volgende stappen uit:

- Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Anti-phishing**. Controleer de lijst met beleidsregels, **hun statuswaarden** en de **prioriteitswaarden.** Als u meer details wilt weergeven, voert u een van de volgende stappen uit:

  - Selecteer het beleid in de lijst en bekijk de details in de flyout.
  - Klik **op Standaardbeleid** en bekijk de details in de flyout.

- Vervang in Exchange Online PowerShell \<Name\> de naam van het beleid of de regel en voer de volgende opdracht uit en verifieer de instellingen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
