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
description: Beheerders kunnen leren hoe ze het anti-phishingbeleid kunnen maken, wijzigen en verwijderen dat beschikbaar is in EOP-organisaties (Exchange Online Protection) met of zonder Exchange Online-postvakken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c277558bad32e1926030483d202b70ae3c910315
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058958"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Antiphishingbeleid configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken is er een standaard anti-phishingbeleid dat een beperkt aantal anti-spoofing-functies bevat die standaard zijn ingeschakeld. Zie Spoofinstellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

Beheerders kunnen het standaard anti-phishingbeleid weergeven, bewerken en configureren (maar niet verwijderen). Voor meer granulariteit kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

Organisaties met Exchange Online-postvakken kunnen anti-phishingbeleid configureren in het Beveiligings- & compliancecentrum of in Exchange Online PowerShell. Zelfstandige EOP-organisaties kunnen alleen gebruikmaken van het Beveiligings- & Compliancecentrum.

Zie Anti-phishingbeleid configureren in Microsoft Defender voor Office 365 voor informatie over het maken en wijzigen van het meer geavanceerde anti-phishingbeleid in Microsoft Defender voor [Office 365.](configure-atp-anti-phishing-policies.md)

De basiselementen van een anti-phishingbeleid zijn:

- **Het anti-phish-beleid:** geeft de phishingbeveiligingen aan die u wilt in- of uitschakelen en de acties om opties toe te passen.
- **De anti-phish-regel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een anti-phish-beleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het beveiligings- & compliancecentrum:

- Wanneer u een anti-phishingbeleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.
- Wanneer u een anti-phishingbeleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de anti-phish-regel. Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.
- Wanneer u een anti-phishingbeleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.

In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk. Zie Exchange Online PowerShell gebruiken om [anti-phishingbeleid](#use-exchange-online-powershell-to-configure-anti-phishing-policies) te configureren verderop in dit artikel voor meer informatie.

Elke organisatie heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:

- Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Als u de effectiviteit van anti-phishingbeveiliging wilt vergroten, kunt u aangepaste anti-phishingbeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

  U kunt anti-phishingbeleid niet beheren in zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u anti-phishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Als u alleen-lezen toegang wilt tot anti-phishingbeleid, moet u lid zijn van de rollengroepen **Globale** lezer of  <sup>\*</sup> Beveiligingslezer.

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De **rollengroep Alleen-weergeven in** [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de <sup>\*</sup> functie.
  - <sup>\*</sup> In het & compliancecentrum kunnen gebruikers met alleen-lezen toegang de instellingen van aangepast anti-phishingbeleid bekijken. Alleen-lezen gebruikers kunnen de instellingen niet zien in het standaard anti-phishingbeleid.

- Als u anti-phishingbeleid wilt maken en wijzigen in zelfstandige EOP, moet u iets doen dat _hydratatie_ vereist voor uw tenant. In het Exchange-beheercentrum (EAC) kunt u  bijvoorbeeld naar het tabblad Machtigingen  gaan, een bestaande rollengroep selecteren, op Pictogram Bewerken bewerken klikken en een rol verwijderen (die u uiteindelijk opnieuw ![ ](../../media/ITPro-EAC-EditIcon.png) toevoegt). Als uw tenant nooit is gehydrateerd, krijgt u een dialoogvenster met de naam **Organisatie-instellingen** bijwerken met een voortgangsbalk die moet worden voltooid. Zie de cmdlet [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) (die niet beschikbaar is in zelfstandige EOP PowerShell of in het Beveiligings- & Compliancecentrum) voor meer informatie over hydratatie.

- Zie Standaardinstellingen voor anti-phishingbeleid voor EOP voor onze aanbevolen instellingen voor [anti-phishingbeleid.](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)

- Maximaal 30 minuten toestaan dat het bijgewerkte beleid wordt toegepast.

- Zie Bestelling en prioriteit van e-mailbeveiliging voor informatie over de toepassing van anti-phishingbeleid in de [filterpijplijn.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Gebruik het beveiligings- & compliancecentrum om anti-phishingbeleid te maken

Als u een aangepast anti-phishingbeleid maakt in het beveiligings- & compliancecentrum, worden de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd gemaakt met dezelfde naam voor beide.

Wanneer u een anti-phishingbeleid maakt, kunt u alleen de naam, beschrijving en het filter voor geadresseerden opgeven waarop het beleid van toepassing is. Nadat u het beleid hebt ingesteld, kunt u het beleid wijzigen om de standaardinstellingen voor anti-phishing te wijzigen of te controleren.

1. Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Klik op **de pagina Anti-phishing** op **Maken.**

3. De **wizard Een nieuw anti-phishingbeleid maken wordt** geopend. Configureer **op de pagina** Naam uw beleid de volgende instellingen:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Wanneer u klaar bent, klikt u op **Volgende.**

4. Op de **pagina Toegepast op** die wordt weergegeven, identificeert u de interne geadresseerden op wie het beleid van toepassing is.

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

5. Controleer uw **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven. U kunt op **Bewerken op elke** instelling klikken om deze te wijzigen.

   Wanneer u klaar bent, klikt u op **Dit beleid maken.**

6. Klik **op OK** in het bevestigingsdialoogvenster dat wordt weergegeven.

Nadat u het anti-phishingbeleid met deze algemene beleidsinstellingen hebt gemaakt, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Gebruik het beveiligings- & compliancecentrum om anti-phishingbeleid te wijzigen

Gebruik de volgende procedures om anti-phishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.

1. Als u er nog niet bent, opent u het Beveiligingscentrum & compliancecentrum en gaat u naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen. Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.

3. Het **fly-out \<name\> Beleid** bewerken wordt weergegeven. Als u in **een** sectie op Bewerken klikt, hebt u toegang tot de instellingen in die sectie.

   - De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in elke volgorde selecteren en wijzigen).

   - Nadat u **in** een sectie op Bewerken hebt geklikt, worden de beschikbare instellingen weergegeven in  een wizard-indeling, maar  u kunt in elke volgorde binnen de pagina's springen en u kunt op Opslaan op een pagina klikken (of  ![ ](../../media/scc-remove-icon.png) **\<name\>** pictogram Annuleren of Sluiten sluiten om terug te keren naar de pagina Uw beleid bewerken (u hoeft niet naar de laatste pagina van de wizard te gaan om op te slaan of te verlaten).

4. **Beleidsinstelling:** Klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u het [beleid](#use-the-security--compliance-center-to-create-anti-phishing-policies) in de vorige sectie maakte:

   - **Naam**
   - **Beschrijving**
   - **Toegepast op**
   - **Uw instellingen controleren**

   Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.

5. **Spoof:** Klik op **Bewerken** om spoofinformatie in of uit te schakelen, identiteitsgegevens van niet-nautische afzenders in Outlook in of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders. Zie Spoofinstellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

   Houd er rekening mee dat deze instellingen ook beschikbaar zijn in anti-phishingbeleid in Defender voor Office 365.

   - **Instellingen voor spoofingfilter:** De standaardwaarde is **Aan** en u wordt aangeraden deze aan te laten staan. Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit.** Zie Spoof [intelligence configureren in EOP voor meer informatie.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar Microsoft 365 gaat. u in plaats daarvan Verbeterde filtering voor verbindingslijnen inschakelen. Zie Verbeterde filtering [voor connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor instructies.

   - **Functie Unauthenticated Sender inschakelen:** De standaardwaarde is **Aan.** Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit.**

   - **Acties:** Geef de actie op die moet worden ondernomen voor berichten die niet worden vervalst:

     **Als e-mail wordt verzonden door iemand die uw** domein niet mag vervalsen:

     - **Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**
     - **Het bericht in quarantaine plaatsen**

   - **Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.

     - U kunt in elke **sectie op Bewerken** klikken om terug te gaan naar de relevante pagina.
     - U kunt de volgende instellingen  rechtstreeks **op** deze pagina in- of uitschakelen:

       - **Antispoofingbeveiliging inschakelen**
       - **Functie Unauthenticated Sender inschakelen**

   Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.

6. Bekijk de instellingen op **de \<Name\> pagina** Uw beleid bewerken en klik vervolgens op **Sluiten.**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Gebruik het beveiligings- & compliancecentrum om het standaard anti-phishingbeleid te wijzigen

Het standaard anti-phishingbeleid heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels. Als u het standaard anti-phishingbeleid wilt wijzigen, gaat u als volgt te werk:

1. Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Klik op **de pagina Anti-phishing** op **Standaardbeleid.**

3. De **pagina Uw beleid bewerken Office365 AntiPhish Default** wordt weergegeven. De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **Imitatie**
   - **Spoof**
   - **Geavanceerde instellingen**

   De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:

   - U kunt  de sectie Beleidsinstelling en -waarden  zien, maar er is geen koppeling Bewerken, dus u kunt de instellingen niet wijzigen (beleidsnaam, beschrijving en op wie het beleid van toepassing is (dit geldt voor alle geadresseerden)).
   - U kunt het standaardbeleid niet verwijderen.
   - U kunt de prioriteit van het standaardbeleid niet wijzigen (dit wordt altijd als laatste toegepast).

4. Controleer op **de pagina Uw beleid bewerken Office365 AntiPhish Default** uw instellingen en klik vervolgens op **Sluiten.**

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aangepaste anti-phishingbeleidsregels in- of uitschakelen

1. Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Let op de waarde in de **kolom Status:**

   - Schuif de schakelknop naar **Uit om** het beleid uit te schakelen.

   - Schuif de schakelknop naar **Aan om** het beleid in te schakelen.

U kunt het standaard anti-phishingbeleid niet uitschakelen.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>De prioriteit instellen van aangepast anti-phishingbeleid

Anti-phishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Aangepaste anti-phishingbeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0). Het standaard anti-phishingbeleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laag** en u kunt deze niet wijzigen.

 **Opmerking:** In het & compliancecentrum kunt u alleen de prioriteit van het anti-phishingbeleid wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).

Als u de prioriteit van  een beleid wilt wijzigen, klikt u op Prioriteit verhogen  of Prioriteit verlagen **in** de eigenschappen van het beleid (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in het Beveiligings- & Compliancecentrum). Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.

1. Ga in het & Compliance center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**

2. Selecteer het beleid dat u wilt wijzigen. Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.

3. Het **fly-out \<name\> Beleid** bewerken wordt weergegeven.

   - Het aangepaste anti-phishingbeleid met **prioriteitswaarde** **0** heeft alleen de **knop Prioriteit verlagen** beschikbaar.

   - Het aangepaste anti-phishingbeleid  met de laagste prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.

   - Als u drie of meer aangepaste anti-phishingbeleidsregels hebt, hebben  beleidsregels  tussen de waarden met de hoogste en laagste prioriteit zowel de knoppen Prioriteit verhogen als Prioriteit verlagen beschikbaar.

4. Klik **op Prioriteit verhogen of** Prioriteit verlagen **om** de waarde Prioriteit **te** wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Het beveiligings- & compliancecentrum gebruiken om anti-phishingbeleid weer te geven

1. Ga in het & compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Ga op een van de volgende stappen te werk:

   - Selecteer een aangepast anti-phishingbeleid dat u wilt weergeven. Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.

   - Klik **op Standaardbeleid** om het standaardbeleid voor anti-phishing te bekijken.

3. Het **fly-out \<name\>** Beleid bewerken wordt weergegeven, waar u de instellingen en waarden kunt bekijken.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Gebruik het beveiligings- & compliancecentrum om anti-phishingbeleid te verwijderen

1. Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Selecteer het beleid dat u wilt verwijderen. Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.

3. Klik in **het \<name\> flyout** Beleid bewerken dat wordt weergegeven op Beleid verwijderen **en** klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Exchange Online PowerShell gebruiken om anti-phishingbeleid te configureren

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

- U kunt de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in het Beveiligings- & Compliancecentrum nadat u het beleid hebt gemaakt:

  - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ `$false` de cmdlet **New-AntiPhishRule).**
  - Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **Nieuw-AntiPhishRule).**

- Een nieuw anti-phish-beleid dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum als u het beleid aan een anti-phish-regel toewijst.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken

Als u een anti-phish-beleid wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
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

- U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._ Wanneer u de naam van een anti-phishingbeleid wijzigt in het Beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de anti-phish-regel.

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

Ga als volgt te werk om te controleren of u anti-phishingbeleid hebt geconfigureerd in Microsoft Defender voor Office 365:

- Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**. Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.** Ga als volgt te werk om meer details weer te geven:

  - Selecteer het beleid in de lijst en bekijk de details in de flyout.
  - Klik **op Standaardbeleid** en bekijk de details in de flyout.

- Vervang in Exchange Online PowerShell de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```