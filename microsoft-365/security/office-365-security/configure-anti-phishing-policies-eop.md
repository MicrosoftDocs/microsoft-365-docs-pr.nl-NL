---
title: Anti-phishings beleid configureren in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u het anti-phishingfilter kunt maken, wijzigen en verwijderen dat beschikbaar is in organisaties met een Exchange Online-bescherming (EOP) met of zonder postvakken van Exchange Online.
ms.openlocfilehash: 66c02513966eda45c4993a28904667f11be225f5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203393"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Anti-phishings beleid configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken is er een standaard anti-phishingfilter met een beperkt aantal anti-spoofings functies die standaard zijn ingeschakeld. Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).

Beheerders kunnen het standaard anti phishingfilter-beleid bekijken, bewerken en configureren (maar niet verwijderen). Voor een betere granulatie kunt u ook een aangepast anti-phishings beleid maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

Organisaties met Exchange Online-postvakken kunnen anti-phishings beleid in het beveiligings & nalevings centrum of in Exchange Online PowerShell configureren. Zelfstandige EOP-organisaties kunnen alleen gebruikmaken van de beveiligings & nalevings centrum.

Zie voor meer informatie over het maken en aanpassen van het meer geavanceerd ATP anti- [virus beleid dat](configure-atp-anti-phishing-policies.md)beschikbaar is in Office 365 Advanced Threat Protection (Office 365 ATP).

De basisonderdelen van een anti phishingfilter zijn:

- **Het anti-virus beleid**: Hiermee geeft u de phishing-beveiliging op om in of uit te schakelen, en de acties voor het toepassen van opties.
- **De anti-phishings regel**: Hiermee geeft u de prioriteiten en de filters voor geadresseerden op (wie het beleid van toepassing is) voor een anti-phishing beleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u een anti-phishing beleid beheert in de beveiligings & nalevings centrum:

- Wanneer u een anti-Phishingfilter maakt, maakt u in feite een anti-phishings regel en het bijbehorende anti-phishings beleid op hetzelfde moment met dezelfde naam voor beide.
- Wanneer u een anti-phishingfilter wijzigt, worden de instellingen voor de naam, prioriteit, ingeschakeld of uitgeschakeld en de filters voor geadresseerden gewijzigd. Alle andere instellingen wijzigen het bijbehorende anti-phishings beleid.
- Wanneer u een anti phishingfilter verwijdert, worden de anti-phishings regel en het bijbehorende anti-onphishings beleid verwijderd.

In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk. Zie voor meer informatie de sectie [Exchange Online PowerShell gebruiken voor het configureren van anti-phishingfilter](#use-exchange-online-powershell-to-configure-anti-phishing-policies) -secties verderop in dit artikel.

Elke organisatie heeft een ingebouwd anti-phishingfilter met de naam Office365 AntiPhish standaard met de volgende eigenschappen:

- Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-avond regel (Recipient filters) gekoppeld aan het beleid.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Voor een grotere effectiviteit van de bescherming tegen phishing is het mogelijk om een aangepast anti-phishings beleid te maken met strikte instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **anti malafide** pagina wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

  U kunt geen anti-phishings beleid beheren in standalone EOP PowerShell.

- U moet machtigingen zijn toegewezen voordat u de procedures in dit artikel kunt uitvoeren:

  - Als u een anti-phishingfilter wilt toevoegen, wijzigen of verwijderen, moet u lid zijn van een van de volgende groepen rollen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezen toegang tot anti phishingfilter moet u lid zijn van een van de volgende rollen groepen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Als u een anti-phishings beleid wilt maken en wijzigen in een zelfstandige EOP, moet u iets doen waarvoor _bidons_ voor uw Tenant is vereist. In het Exchange-Beheercentrum gaat u bijvoorbeeld naar het tabblad **machtigingen** , selecteert u een bestaande rollen groep, klikt u op **Edit** ![ pictogram bewerken bewerken ](../../media/ITPro-EAC-EditIcon.png) en verwijdert u een functie (die u uiteindelijk later gaat toevoegen). Als uw Tenant nooit is gehydrateerd, krijgt u een dialoogvenster met de naam **organisatie-instellingen bijwerken** met een voortgangsbalk die succesvol moet worden voltooid. Als u meer wilt weten over bidons, raadpleegt u de cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (die niet beschikbaar is in een zelfstandige EOP PowerShell of in het beveiligings & nalevings centrum).

- Voor de aanbevolen instellingen voor het anti-phishings beleid raadpleegt u [EOP standaard anti phishingfilter-beleidsinstellingen](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

- Maximaal 30 minuten toegestaan voor het nieuwe beleid dat u wilt toepassen.

- Zie de [volgorde en prioriteit van e-mail beveiliging](how-policies-and-protections-are-combined.md)voor informatie over waar anti phishingfilter in de filter pijplijn wordt toegepast.

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Beveiligings & voor compliance gebruiken om een anti-phishings beleid te maken

Als u een aangepast anti-Phishingfilter maakt in het compliance-& Beveiligingscentrum, maakt u op hetzelfde moment de anti-phishing regel en het bijbehorende anti-phishings beleid met dezelfde naam voor beide.

Wanneer u een anti Phishingfilter maakt, kunt u alleen de Beleidsnaam, de beschrijving en het filter voor de ontvanger opgeven waarmee wordt aangegeven voor wie het beleid van toepassing is. Nadat u het beleid hebt gemaakt, kunt u het beleid wijzigen, zodat u de standaardinstellingen voor anti phishing kunt wijzigen of bekijken.

1. Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing**beleid voor Threat Management.

2. Op de **anti phishing** -pagina klikt u op **maken**.

3. De wizard **nieuw anti-phishingfilterbeleid maken** wordt geopend. Configureer de volgende instellingen op de pagina **naam van uw beleid** :

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Wanneer u klaar bent, klikt u op **volgende**.

4. Op de pagina **toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden waarop het beleid van toepassing is.

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

5. Controleer de instellingen op de pagina **uw instellingen bekijken** die wordt weergegeven. U kunt op de verschillende instellingen klikken om de **bewerking** te wijzigen.

   Wanneer u klaar bent, klikt u op **dit beleid maken**.

6. Klik op **OK** in het bevestigingsvenster dat wordt weergegeven.

Nadat u het anti phishingfilter met deze algemene beleidsinstellingen hebt gemaakt, volgt u de instructies in het volgende gedeelte om de beveiligingsinstellingen in het beleid te configureren.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>De beveiligings & voor compliance gebruiken om een anti-phishings beleid te wijzigen

Gebruik de volgende procedures om een anti-phishingfilter te wijzigen: een nieuwe beleidsregels die u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.

1. Als u dit nog niet hebt gedaan, opent u het beveiligings & nalevings centrum en gaat u naar beleid voor **Threat Management** \> **Policy** \> **anti-phishing**.

2. Selecteer het aangepaste anti-phishingfilter dat u wilt wijzigen. Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.

3. De flyout **uw beleid \<name\> bewerken** wordt weergegeven. Als u in een sectie op **bewerken** klikt, krijgt u toegang tot de instellingen in deze sectie.

   - De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in een willekeurige volgorde selecteren en wijzigen).

   - Nadat u op **bewerken** in een sectie hebt geklikt, worden de beschikbare instellingen in de wizard indeling weergegeven, maar u kunt wel binnen de pagina's in een willekeurige Volg **Cancel** orde springen **Close** , en u kunt op de pagina **Opslaan** of sluiten klikken op het pictogram voor het ![ ](../../media/scc-remove-icon.png) **bewerken van uw beleid \<name\> ** (u hoeft niet te klikken op de laatste pagina van de wizard om de pagina te openen

4. **Beleidsinstelling**: Klik op **bewerken** als u de instellingen wilt wijzigen die beschikbaar waren wanneer u [het beleid hebt gemaakt](#use-the-security--compliance-center-to-create-anti-phishing-policies) in de vorige sectie:

   - **Naam**
   - **Beschrijving**
   - **Toegepast op**
   - **De instellingen bekijken**

   Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.

5. **Spoof**: Klik op **bewerken** als u de identiteit van spoofing wilt in-of uitschakelen, schakel de identificatie van niet-geverifieerde afzenders in Outlook in of uit en configureer de actie die u wilt toepassen op berichten van geblokkeerde vervalste afzenders. Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).

   Deze instellingen zijn ook beschikbaar in het ATP anti-phishings beleid.

   - **Instellingen voor spoofing filter**: de standaardwaarde is **ingeschakeld**en u wordt aangeraden deze in te stellen. Verschuif de wissel **knop om deze**uit te schakelen. Zie voor meer informatie [spoof Intelligence configureren in EOP](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > U hoeft geen anti-spoofing-beveiliging uit te schakelen als uw MX-record niet verwijst naar Microsoft 365. u kunt in plaats hiervan uitgebreid filteren op connectors. Zie voor meer informatie het artikel [uitgebreid filteren op connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Functie niet-geverifieerde afzender inschakelen**: de standaardwaarde is **ingeschakeld**. Verschuif de wissel **knop om deze**uit te schakelen.

   - **Acties**: de actie opgeven die moet worden uitgevoerd voor berichten die geen spoof Intelligence hebben:

     **Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen, doet u het**volgende:

     - **Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde**
     - **Het bericht Quarantine**

   - **Controleer uw instellingen**: in plaats van op elke afzonderlijke stap te klikken, worden de instellingen in een overzicht weergegeven.

     - U kunt in elke sectie op **bewerken** klikken om terug te gaan naar de gewenste pagina.
     - U kunt de volgende instellingen rechtstreeks op deze pagina **in** -of **uitschakelen** :

       - **Antispoofing-beveiliging inschakelen**
       - **Niet-geverifieerde afzender functie inschakelen**

   Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.

6. Ga op de pagina ** \<Name\> beleid bewerken** naar de instellingen en klik op **sluiten**.

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Met behulp van het nalevings centrum voor beveiliging & u het standaard anti-phishingfilter beleid wijzigen

Het standaard anti-Phishingfilter wordt de naam Office365 AntiPhish standaard genoemd en wordt niet weergegeven in de lijst met beleidsregels. Ga als volgt te werk om het standaard anti-phishingfilter te wijzigen:

1. Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing**beleid voor Threat Management.

2. Klik op de pagina **anti phishing** op **standaardbeleid**.

3. De standaardpagina voor het **bewerken van uw beleid Office365 AntiPhish** wordt weergegeven. De volgende secties zijn beschikbaar, met een identieke instelling voor [het wijzigen van een aangepast beleid](#use-the-security--compliance-center-to-modify-anti-phishing-policies).

   - **Imitatie**
   - **Met**
   - **Geavanceerde instellingen**

   De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:

   - U ziet de secties en waarden van de **beleidsinstelling** , maar er is geen koppeling voor **bewerken** , zodat u de instellingen (Beleidsnaam en beschrijving, en wie het beleid van toepassing is op alle geadresseerden), niet kunt wijzigen.
   - U kunt het standaardbeleid niet verwijderen.
   - Het is niet mogelijk om de prioriteit van het standaardbeleid te wijzigen (dit wordt altijd als laatste toegepast).

4. Controleer de instellingen op de pagina **uw beleid Office365 AntiPhish standaard** instellen en klik op **sluiten**.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aangepast anti-phishings beleid in-of uitschakelen

1. Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing**beleid voor Threat Management.

2. Let op de waarde in de kolom **status** :

   - Schuif de wisselknop naar **uit** om het beleid uit te schakelen.

   - Schuif de wisselknop naar **aan om het beleid in te** schakelen.

U kunt het standaard anti-Phishingfilter niet uitschakelen.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>De prioriteit van een aangepast anti-phishings beleid instellen

Standaard krijgt u een anti-phishingfilter met een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels zijn een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Een aangepast anti-phishings beleid wordt weergegeven in de volgorde waarin ze worden verwerkt ( **het eerste** beleid heeft de waarde 0). Het standaard anti-phishingfilter met de naam Office365 AntiPhish standaard heeft de waarde van een aangepaste **prioriteit en kunt**deze niet wijzigen.

 **Opmerking**: in het beveiligings & nalevings centrum kunt u de prioriteit van het anti phishingfilter wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit negeren wanneer u de regel voor de anti-phishing maakt (die van invloed kunnen zijn op de prioriteit van bestaande regels).

Als u de prioriteit van een beleid wilt wijzigen, klikt u op **prioriteit verhogen** of **prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **prioriteits** nummer niet rechtstreeks wijzigen in de beveiligings & compliance Center). Als u meerdere beleidsregels hebt, kunt u de prioriteit van een beleid alleen wijzigen.

1. Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.

2. Selecteer het beleid dat u wilt wijzigen. Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.

3. De flyout **uw beleid \<name\> bewerken** wordt weergegeven.

   - Het aangepaste anti-phishingfilter met de **prioriteits** waarde **0** heeft slechts de knop **prioriteit verlagen** .

   - Het aangepaste anti-phishingfilter met de laagste **prioriteits** waarde (bijvoorbeeld **3**) is slechts de knop **prioriteit verhogen** beschikbaar.

   - Als u beschikt over drie of meer aangepaste anti phishingfilter-beleidsregels, hebben beleidsregels tussen de hoogste en laagste prioriteit de knoppen **prioriteit verhogen** en **prioriteit verlagen** .

4. Klik op **prioriteit verhogen** of **prioriteit verkleinen** om de **prioriteits** waarde te wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Het Beveiligingscentrum voor beveiliging & gebruiken om anti phishingfilter te bekijken

1. Ga in het beveiligings & compliance Center naar het beleid voor **bedreigings beheer** en ga \> **Policy** \> **tegen phishing**.

2. Voer een van de volgende stappen uit:

   - Selecteer een aangepast anti-phishingfilter dat u wilt bekijken. Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.

   - Klik op **standaardbeleid** om het standaard anti-phishingfilter te bekijken.

3. De flyout voor het **beleid \<name\> bewerken** wordt weergegeven, waarin u de instellingen en waarden kunt weergeven.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>De beveiligings & gebruiken om anti phishings beleid te verwijderen

1. Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing**beleid voor Threat Management.

2. Selecteer het beleid dat u wilt verwijderen. Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.

3. Klik in het vervolgmenu **uw beleidsregels \<name\> bewerken** dat wordt weergegeven op **beleid verwijderen**en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Een anti phishingfilter configureren met Exchange Online PowerShell

Zoals hierboven beschreven, bestaat een anti-phishings beleid en een anti-phishings regel.

In Exchange Online PowerShell is het verschil tussen anti-malwarebeleid en anti-phishing regels zichtbaar. U een anti-phishings beleid beheert met behulp van de cmdlets ** \* AntiPhishPolicy** en u beheert de anti-phishings regels met behulp van de cmdlets voor ** \* AntiPhishRule** .

- In PowerShell maakt u eerst het anti-phishings beleid en vervolgens maakt u een anti-phishings regel waarmee het beleid wordt aangegeven waarop de regel van toepassing is.
- In PowerShell wijzigt u de instellingen van het anti-phishings beleid en de anti-phishing regel afzonderlijk.
- Wanneer u een anti-phishings beleid verwijdert uit PowerShell, wordt de overeenkomstige anti-phishing regel niet automatisch verwijderd en vice versa.

> [!NOTE]
> De volgende PowerShell-procedures zijn niet beschikbaar in zelfstandige EOP-organisaties die gebruikmaken van Exchange Online Protection PowerShell.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell gebruiken om een anti-phishings beleid te maken

Het maken van een anti-phishingfilter in PowerShell is een procedure die bestaat uit twee stappen:

1. Maak het anti-phishings beleid.
2. Maak de anti-phishings regel waarmee het anti-phishings beleid wordt aangegeven waarop de regel van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe anti-phishings regel maken en er een bestaande, niet-bijbehorend anti-phishings beleid aan toewijzen. Een anti-phishings regel kan niet worden gekoppeld aan meer dan een anti-phishings beleid.

- U kunt de volgende instellingen configureren voor nieuwe anti-phishings beleidsregels in PowerShell die niet beschikbaar zijn in het beveiligings & compliance Center totdat u het beleid hebt gemaakt:

  - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld_ `$false` in de **nieuwe AntiPhishRule-** cmdlet).
  - De prioriteit van het beleid instellen voor het maken_Priority_ van de _\<Number\>_ **nieuwe AntiPhishRule-** cmdlet (prioriteit).

- Een nieuw anti-phishings beleid dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een anti-phishing regel toewijst.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Stap 1: PowerShell gebruiken om een anti-phishings beleid te maken

Voor het maken van een anti-phishings beleid gebruikt u de volgende syntaxis:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

In het volgende voorbeeld wordt een anti-phishings beleid met de naam onderzoek Quarantine gemaakt met de volgende instellingen:

- De beschrijving luidt: afdelings beleid voor onderzoek.
- Wijzigt de standaardactie voor spoofing in Quarantine.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Zie [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Stap 2: PowerShell gebruiken om een anti-phishings regel te maken

Voor het maken van een anti-phishing regel gebruikt u de volgende syntaxis:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een anti-phishing regel genaamd onderzoek afdeling met de volgende voorwaarden gemaakt:

- De regel is verbonden met het anti-phishings beleid met de naam onderzoek quarantaine.
- De regel geldt voor de leden van de groep met de naam onderzoek afdeling.
- Aangezien we de _prioriteits_ parameter niet gebruiken, wordt de standaardprioriteit gebruikt.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Zie [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell gebruiken om een anti-phishings beleid te bekijken

Gebruik de volgende syntaxis om de bestaande anti-phishings beleidsregels te bekijken:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle anti-phishing-beleidsregels en de opgegeven eigenschappen geretourneerd.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In het volgende voorbeeld worden alle eigenschapswaarden geretourneerd voor het anti-phishings beleid met de naam leidinggevenden.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell gebruiken om anti-phishings regels te bekijken

Gebruik de volgende syntaxis om bestaande anti-phishings regels weer te geven:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In het volgende voorbeeld wordt een overzichtslijst met alle anti-phishing regels met de opgegeven eigenschappen geretourneerd.

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

In het volgende voorbeeld worden alle eigenschapwaarden voor de anti-phishing-regel genaamd contoso leidinggevenden geretourneerd.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell gebruiken om een anti-phishings beleid te wijzigen

Met uitzondering van de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phishings beleid in PowerShell aanpast wanneer u een beleid maakt zoals wordt beschreven in [stap 1: PowerShell gebruiken om een anti-phishings beleid te maken](#step-1-use-powershell-to-create-an-anti-phish-policy) eerder in dit artikel.

- De schakeloptie _MakeDefault_ waarmee het opgegeven beleid wordt omgezet in het standaardbeleid (voor iedereen, de **laagste** prioriteit en het niet verwijderen) is alleen beschikbaar wanneer u een anti-Echobeleid wijzigt in PowerShell.

- U kunt niet de naam van een anti-phishings beleid wijzigen (de cmdlet **set-AntiPhishPolicy** heeft geen _naam_ parameter). Wanneer u de naam van een anti-phishingfilter wijzigt in de beveiligings & nalevings centrum, kunt u de naam van de anti-phishing _regel_alleen wijzigen.

Voor het wijzigen van een anti-phishings beleid gebruikt u de volgende syntaxis:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Zie [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell gebruiken om anti-phishings regels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een anti-phishing regel wijzigt in PowerShell is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande anti-Phish regels wilt in-of uitschakelen.

U kunt ook dezelfde instellingen gebruiken als u een regel maakt zoals wordt beschreven in [stap 2: PowerShell gebruiken voor het maken van een anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) sectie, eerder in dit artikel.

Gebruik de volgende syntaxis om een anti-phishing regel te wijzigen:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Zie [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell gebruiken om anti-phishings regels in of uit te schakelen

Wanneer u een anti-phishing regel in-of uitschakelt in PowerShell, schakelt u het volledige anti-phishings beleid in of uit (de anti-phishings regel en het door u toegekende anti-phishings beleid). U kunt het standaard anti-phishingfilter-beleid niet in-of uitschakelen (het wordt altijd toegepast op alle geadresseerden).

U kunt een anti-phishings regel in PowerShell in-of uitschakelen met behulp van de volgende syntaxis:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de anti-phishing regel genaamd marketing afdeling uitgeschakeld.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell gebruiken om de prioriteit van anti-phishings regels in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit wilt instellen van een anti-Phish regel in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Opmerkingen**:

- Als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-AntiPhishRule** .

- Het anti-phishings beleid heeft geen overeenkomstige anti-phishings regel, en het is altijd de **laagste**ongewijzigde prioriteitswaarde.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell gebruiken om een anti-phishings beleid te verwijderen

Wanneer u PowerShell gebruikt om een anti-phishings beleid te verwijderen, wordt de overeenkomstige anti-phishings regel niet verwijderd.

Gebruik de volgende syntaxis om een anti-phishings beleid te verwijderen in PowerShell:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het anti-phishings beleid met de naam marketing afdeling verwijderd.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Zie [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell gebruiken om anti-phishings regels te verwijderen

Als u PowerShell gebruikt om een anti-phishing regel te verwijderen, wordt het bijbehorende anti-phishings beleid niet verwijderd.

Gebruik de volgende syntaxis om een anti-phishings regel te verwijderen in PowerShell:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de anti-phishing regel genaamd marketing afdeling verwijderd.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Zie [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Voer een of meer van de volgende stappen uit om te controleren of u het juiste beleid voor het gebruik van ATP anti phishing hebt geconfigureerd:

- Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **anti-phishing**beleid voor Threat Management. Controleer de lijst met beleidsregels, de **status** waarden en de waarden van de **prioriteit** . Ga op een van de volgende manieren te werk om meer informatie weer te geven:

  - Selecteer een beleid in de lijst en Bekijk de details in de vervolgkeuzelijst.
  - Klik op **standaardbeleid** en Bekijk de details in het vervolgmenu.

- In Exchange Online PowerShell vervangt u de \<Name\> naam van het beleid of de regel door de volgende opdracht uit te voeren en de instellingen te controleren:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
