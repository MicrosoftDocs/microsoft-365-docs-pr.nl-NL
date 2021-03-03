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
description: Beheerders kunnen informatie krijgen over het maken, wijzigen en verwijderen van het anti-phishingbeleid dat beschikbaar is in Exchange Online Protection-organisaties (EOP) met of zonder postvakken van Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 612c7153f89a404cac736a9a46e8ca5f69e46f65
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406218"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>Antiphishingbeleid configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken is er een standaard anti-phishingbeleid dat een beperkt aantal functies voor anti-spoofing bevat die standaard zijn ingeschakeld. Zie Spoof-instellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

Beheerders kunnen het standaard anti-phishingbeleid bekijken, bewerken en configureren (maar niet verwijderen). Voor een grotere granulatie kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

Organisaties met Exchange Online-postvakken kunnen anti-phishingbeleid configureren in het beveiligings- & compliancecentrum of in Exchange Online PowerShell. Zelfstandige EOP-organisaties kunnen alleen gebruikmaken van het & compliancecentrum.

Zie Anti-phishingbeleid configureren in Microsoft Defender voor Office 365 voor meer informatie over het maken en wijzigen van het geavanceerde anti-phishingbeleid in Microsoft Defender voor Office 365 dat beschikbaar is in Defender voor [Office 365.](configure-atp-anti-phishing-policies.md)

De basiselementen van een anti-phishingbeleid zijn:

- **Het anti-phish-beleid:** geeft aan welke phishingbeveiliging moet worden ingeschakeld of uitgeschakeld, en wat er moet worden ondernomen om opties toe te passen.
- **De anti-phish-regel:** geeft de prioriteit- en ontvangerfilters (op wie het beleid van toepassing is) voor een anti-phish-beleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het beveiligings- & compliancecentrum:

- Wanneer u een anti-phishingbeleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.
- Wanneer u een anti-phishingbeleid wijzigt, worden instellingen met betrekking tot de naam, prioriteit, in- of uitgeschakeld en filters voor geadresseerden gewijzigd in de anti-phish-regel. Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.
- Wanneer u een anti-phishingbeleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.

In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Exchange Online PowerShell gebruiken voor het configureren van [anti-phishingbeleid](#use-exchange-online-powershell-to-configure-anti-phishing-policies) verderop in dit artikel voor meer informatie.

Elke organisatie heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default dat de volgende eigenschappen heeft:

- Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook als er geen anti-phish-regel (geadresseerdenfilters) aan het beleid is gekoppeld.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

U kunt de effectiviteit van de beveiliging tegen phishing vergroten door een aangepast anti-phishingbeleid te maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **anti-phishing-pagina** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

  U kunt geen anti-phishingbeleid beheren in zelfstandige EOP PowerShell.

- U moet machtigingen toegewezen krijgen in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u anti-phishingbeleid wilt toevoegen, wijzigen **en** verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.
  - Voor alleen-lezen toegang tot anti-phishingbeleid moet u  lid zijn van de rollengroepen Globale lezer of  <sup>\*</sup> Beveiligingslezer.

  Zie Machtigingen [in Exchange Online voor meer informatie.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)

  **Opmerkingen**:

  - Als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol  in het Microsoft 365-beheercentrum, krijgen gebruikers de vereiste machtigingen en machtigingen voor andere functies in Microsoft 365. Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De **rollengroep Organisatiebeheer alleen-weergeven** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) biedt ook alleen-lezen toegang tot de <sup>\*</sup> functie.
  - <sup>\*</sup> In het & Compliancecentrum kunnen gebruikers met alleen-lezen-toegang de instellingen van aangepaste anti-phishingbeleidsregels bekijken. Alleen-lezen gebruikers kunnen de instellingen in het standaard anti-phishingbeleid niet zien.

- Als u anti-phishingbeleid wilt maken en wijzigen in de zelfstandige EOP, moet u iets doen wat voor uw tenant _vereist_ is. In het Exchange-beheercentrum kunt u bijvoorbeeld naar  het tabblad Machtigingen gaan, een  bestaande rollengroep selecteren, op het pictogram Bewerken klikken en een rol verwijderen (die u uiteindelijk weer ![ toevoegt). ](../../media/ITPro-EAC-EditIcon.png) Als uw tenant nog nooit gesaneerd  is, krijgt u een dialoogvenster met de naam Organisatie-instellingen bijwerken met een voortgangsbalk die zou moeten worden voltooid. Zie de cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (die niet beschikbaar is in zelfstandige EOP PowerShell of in het beveiligings- & Compliancecentrum) voor meer informatie over bez.

- Zie de standaardinstellingen voor anti-phishingbeleid via EOP voor [de aanbevolen instellingen voor anti-phishingbeleid.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

- Het kan 30 minuten duren voordat het bijgewerkte beleid wordt toegepast.

- Zie Volgorde en prioriteit van e-mailbeveiliging voor informatie over waar anti-phishingbeleid wordt toegepast in de [filterpijplijn.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>Het beveiligings- & voor het maken van anti-phishingbeleidsregels

Als u een aangepast anti-phishingbeleid maakt in het beveiligings- & Compliancecentrum, worden de anti-phish-regel en het bijbehorende anti-phish-beleid op hetzelfde moment met dezelfde naam voor beide gemaakt.

Wanneer u een anti-phishingbeleid maakt, kunt u alleen de beleidsnaam, beschrijving en het filter voor geadresseerden opgeven waarop het beleid van toepassing is. Nadat u het beleid hebt ingesteld, kunt u het beleid wijzigen om de standaardinstellingen voor anti-phishing te wijzigen of te controleren.

1. Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**

2. Klik op **de anti-phishing-pagina** op **Maken.**

3. De **wizard Een nieuw anti-phishingbeleid maken wordt** geopend. Configureer **de volgende instellingen op** de pagina Uw beleid een naam geven:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Klik op Volgende wanneer u klaar **bent.**

4. Zoek op **de** pagina Toegepast op die wordt weergegeven naar de interne geadresseerden op wie het beleid van toepassing is.

   U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

   Klik **op Voorwaarde toevoegen.** Selecteer in de vervolgkeuzepkeuze die wordt weergegeven een voorwaarde onder **Toegepast als:**

   - **De geadresseerde is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactcontacten in uw organisatie op.
   - **De geadresseerde is lid van:** Geeft een of meer groepen in uw organisatie op.
   - **Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie.

   Nadat u de voorwaarde hebt geselecteerd, wordt een bijbehorende vervolgkeuzekeuze verschijnen met een **Van deze** vakjes.

   - Klik in het vak en blader door de lijst met waarden die u wilt selecteren.
   - Klik in het vak en begin te typen om de lijst te filteren en selecteer een waarde.
   - Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.
   - Als u afzonderlijke items wilt verwijderen, klikt **u op het** pictogram Verwijderen van de ![ ](../../media/scc-remove-icon.png) waarde.
   - Als u de hele voorwaarde wilt verwijderen, klikt **u op het pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) voorwaarde.

   Als u een extra voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als.**

   Als u uitzonderingen wilt toevoegen, klikt u **op Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als.** De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Klik op Volgende wanneer u klaar **bent.**

5. Controleer de **instellingen op de** pagina Uw instellingen controleren die wordt weergegeven. U kunt bij **elke** instelling op Bewerken klikken om deze te wijzigen.

   Klik op Dit beleid maken **wanneer u klaar bent.**

6. Klik **op OK** in het bevestigingsvenster dat wordt weergegeven.

Nadat u het anti-phishingbeleid met deze algemene beleidsinstellingen hebt gemaakt, volgt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>Gebruik het beveiligings- & om anti-phishingbeleid te wijzigen

Gebruik de volgende procedures om anti-phishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaand beleid dat u al hebt aangepast.

1. Als u er nog niet bent, opent u het beveiligingscentrum & compliancecentrum en gaat u **naar** Het beleid voor bedreigingsbeheer \>  \> **anti-phishing.**

2. Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen. Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.

3. De **flyout \<name\> Uw beleid** bewerken wordt weergegeven. Als u **in een** sectie op Bewerken klikt, hebt u toegang tot de instellingen in die sectie.

   - De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in elke volgorde selecteren en wijzigen).

   - Nadat u in een sectie op Bewerken hebt geklikt, worden de beschikbare instellingen weergegeven in  een wizard-indeling,  maar  u kunt in elke gewenste volgorde binnen de pagina's springen en u kunt klikken op Opslaan op een pagina (of  ![ ](../../media/scc-remove-icon.png) **\<name\>** het pictogram Annuleren of Sluiten om terug te keren naar de pagina Uw beleid bewerken (u hoeft niet naar de laatste pagina van de wizard te gaan om deze op te slaan of te verlaten).

4. **Beleidsinstelling:** klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u [het](#use-the-security--compliance-center-to-create-anti-phishing-policies) beleid in de vorige sectie maakte:

   - **Naam**
   - **Beschrijving**
   - **Toegepast op**
   - **Uw instellingen controleren**

   Klik op een pagina op Opslaan **wanneer** u klaar bent.

5. **Spoof:**  klik op Bewerken om spoof intelligence in of uit te schakelen, identificatie van afzenders met niet-geauteerde afzender in Outlook in of uit te schakelen en de actie zo te configureren dat deze van toepassing is op berichten van geblokkeerde afzenders met spoofing. Zie Spoof-instellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

   Dezelfde instellingen zijn ook beschikbaar in anti-phishingbeleid in Defender voor Office 365.

   - **Instellingen voor adresvervalsingsfilters:** de standaardwaarde is **Aan** en het is raadzaam deze ingeschakeld te laten. Zet de schakelaar op Uit om deze uit **te schakelen.** Zie Spoof Intelligence configureren in EOP voor [meer informatie.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > U hoeft beveiliging tegen adresvervalsing niet uit te schakelen als uw MX-record niet naar Microsoft 365 betekent. hebt u in plaats daarvan Enhanced Filtering for Connectors ingeschakeld. Zie [Enhanced Filtering for Connectors in Exchange Online voor instructies.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **Functie Niet-geauteerde afzender inschakelen:** de standaardwaarde is **Ingeschakeld.** Zet de schakelaar op Uit om deze uit **te schakelen.**

   - **Acties:** geef de actie op die moet worden ondernomen op berichten waarin spoof intelligence mislukt:

     **Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen:**

     - **Bericht verplaatsen naar de mappen voor ongewenste e-mail van de geadresseerden**
     - **Het bericht in quarantaine plaatsen**

   - **Controleer de instellingen:** in plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.

     - U kunt in **elke sectie op** Bewerken klikken om terug te gaan naar de relevante pagina.
     - U kunt de volgende instellingen rechtstreeks **op** deze pagina **in-** of uitschakelen:

       - **Beveiliging tegen antispoofing inschakelen**
       - **Functie Niet-geauteerde afzender inschakelen**

   Klik op een pagina op Opslaan **wanneer** u klaar bent.

6. Ga terug naar **de pagina Uw beleid bewerken, \<Name\>** controleer de instellingen en klik op **Sluiten.**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Het beveiligings- & om het standaard anti-phishingbeleid te wijzigen

Het standaardbeleid tegen phishing heet Office 365 Antiphish Default en wordt niet weergegeven in de lijst met beleidsregels. Ga als volgt te werk om het standaardbeleid tegen phishing te wijzigen:

1. Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**

2. Klik op **de pagina Anti-phishing** op **Standaardbeleid.**

3. De **pagina Uw beleid bewerken in Office 365 Antiphish Default** wordt weergegeven. De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)

   - **Imitatie**
   - **Spoof**
   - **Geavanceerde instellingen**

   De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:

   - U kunt  de sectie en waarden van de  beleidsinstelling zien, maar er is geen koppeling Bewerken. U kunt dus de instellingen (beleidsnaam, beschrijving en op wie het beleid van toepassing is) niet wijzigen (dit geldt voor alle geadresseerden)).
   - U kunt het standaardbeleid niet verwijderen.
   - U kunt de prioriteit van het standaardbeleid niet wijzigen (dit wordt altijd als laatste toegepast).

4. Controleer de instellingen op de pagina Uw beleid bewerken in **Office 365 Antiphish Default** en klik op **Sluiten.**

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Aangepaste anti-phishingbeleidsregels in- of uitschakelen

1. Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**

2. U ziet de waarde in de **kolom Status:**

   - Schuif de schakelknop naar **Uit om** het beleid uit te schakelen.

   - Schuif de schakelknop naar **Aan om** het beleid in te schakelen.

U kunt het standaard anti-phishingbeleid niet uitschakelen.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>De prioriteit van aangepast anti-phishingbeleid instellen

Anti-phishingbeleidsregels krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Aangepaste anti-phishing-beleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid **heeft** de prioriteitswaarde 0). Het standaard antiphish-beleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteit **Laagste** en u kunt deze niet wijzigen.

 **Opmerking:** in het & compliancecentrum kunt u de prioriteit van het anti-phishingbeleid alleen wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die de prioriteit van bestaande regels kan beïnvloeden).

Als u de prioriteit van  een beleid wilt wijzigen, klikt u **in** de eigenschappen  van het beleid op Hogere prioriteit of Prioriteit verlagen (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in het beveiligings- & compliancecentrum). Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.

1. Ga in het & compliancecentrum naar  \>  \> **RISICOBEHEERBELEID ATP anti-phishing.**

2. Selecteer het beleid dat u wilt wijzigen. Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.

3. De **flyout \<name\> Uw beleid** bewerken wordt weergegeven.

   - Voor het aangepaste anti-phishingbeleid met **prioriteitswaarde** **0** is alleen de **knop** Prioriteit verlagen beschikbaar.

   - Voor het aangepaste anti-phishingbeleid met de **laagste** prioriteitswaarde  (bijvoorbeeld **3)** is alleen de knop Prioriteit verhogen beschikbaar.

   - Als u drie of meer aangepaste anti-phishingbeleidsregels hebt, zijn  voor beleid tussen de hoogste en laagste prioriteit de knoppen Hogere prioriteit en Prioriteit **verlagen** beschikbaar.

4. Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>Het beveiligings- & compliancecentrum gebruiken om anti-phishingbeleid te bekijken

1. Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**

2. Ga op een van de volgende stappen te werk:

   - Selecteer een aangepast anti-phishingbeleid dat u wilt bekijken. Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.

   - Klik **op Standaardbeleid** om het standaardbeleid tegen phishing te bekijken.

3. De **flyout \<name\> Uw beleid** bewerken wordt weergegeven, waarin u de instellingen en waarden kunt bekijken.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>Het beveiligings- &-compliancecentrum gebruiken om anti-phishingbeleid te verwijderen

1. Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.**

2. Selecteer het beleid dat u wilt verwijderen. Als de selectie al is ingeschakeld, moet u de selectie ongedaan maken en opnieuw selecteren.

3. Klik in **de \<name\>** flyout Uw beleid bewerken die wordt weergegeven op Beleid verwijderen en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Exchange Online PowerShell gebruiken om anti-phishingbeleid te configureren

Zoals eerder is beschreven, bestaat een anti-phishingbeleid uit een anti-phish-beleid en een anti-phish-regel.

In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk. U beheert anti-phish-beleid met behulp van de **\* cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de cmdlets **\* -AntiPhishRule.**

- In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel die bepaalt op welke beleidsregel de regel van toepassing is.
- In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.
- Wanneer u een anti-phish-beleid uit PowerShell verwijdert, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.

> [!NOTE]
> De volgende PowerShell-procedures zijn niet beschikbaar in zelfstandige EOP-organisaties die Exchange Online Protection PowerShell gebruiken.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell gebruiken om anti-phishingbeleid te maken

Het maken van een anti-phishingbeleid in PowerShell bestaat uit twee stappen:

1. Maak het anti-phish-beleid.
2. Maak de anti-phish-regel die het anti-phish-beleid aangeeft waar de regel op van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe anti-phish-regel maken en er een bestaand, niet-verbonden anti-phish-beleid aan toewijzen. Een anti-phish-regel kan niet worden gekoppeld aan meer dan één anti-phish-beleid.

- U kunt de volgende instellingen configureren voor nieuw anti-phish-beleid in PowerShell die pas beschikbaar zijn in het beveiligings- &-compliancecentrum nadat u het beleid hebt gemaakt:

  - Het nieuwe beleid maken dat is uitgeschakeld _(ingeschakeld_ `$false` op de cmdlet **New-AntiPhishRule).**
  - De prioriteit van het beleid instellen tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **New-AntiPhishRule).**

- Een nieuw anti-phish-beleid dat u in PowerShell maakt, is pas zichtbaar in het compliancecentrum voor beveiligings- & wanneer u het beleid toewijst aan een anti-phish-regel.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken

Gebruik deze syntaxis om een anti-phish-beleid te maken:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

In dit voorbeeld wordt een anti-phish-beleid gemaakt met de naam Research Quarantine met de volgende instellingen:

- De beschrijving is: het beleid van de onderzoeksafdeling.
- Wijzigt de standaardactie voor spoofing in quarantaine.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

Zie [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Stap 2: PowerShell gebruiken om een anti-phish-regel te maken

Gebruik de volgende syntaxis om een anti-phish-regel te maken:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een anti-phish-regel gemaakt genaamd Onderzoeksafdeling met de volgende voorwaarden:

- De regel is gekoppeld aan het anti-phish-beleid met de naam Research Quarantine.
- De regel is van toepassing op leden van de groep genaamd Onderzoeksafdeling.
- Omdat we de parameter Prioriteit niet _gebruiken,_ wordt de standaardprioriteit gebruikt.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Zie [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid weer te geven

Gebruik de volgende syntaxis om bestaand anti-phish-beleid te bekijken:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst van alle anti-phish-beleidsregels samen met de opgegeven eigenschappen weergegeven.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In dit voorbeeld worden alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden als retourneert.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels weer te geven

Gebruik de volgende syntaxis als u bestaande anti-phish-regels wilt weergeven:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst van alle anti-phish-regels samen met de opgegeven eigenschappen weergegeven.

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

In dit voorbeeld worden alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Leidinggevenden als retourneert.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid te wijzigen

Met andere opties dan de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u een beleid maakt zoals wordt beschreven in stap 1: PowerShell gebruiken om een [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) te maken eerder in dit artikel.

- De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (voor iedereen geldt, altijd de laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.

- U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._ Wanneer u de naam van een anti-phishingbeleid wijzigt in het beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de anti-phish-regel.

Gebruik de volgende syntaxis om een anti-phish-beleid te wijzigen:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-AntiPhishPolicy voor gedetailleerde syntaxis- en parameterinformatie.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de ingeschakelde _parameter_ waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.

Anders zijn dezelfde instellingen beschikbaar wanneer u een regel maakt, zoals wordt beschreven in stap 2: PowerShell gebruiken om een sectie met [anti-phish-regels](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken eerder in dit artikel.

Gebruik de volgende syntaxis om een anti-phish-regel te wijzigen:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Zie [Set-AntiPhishRule voor](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels in of uit te schakelen

Door een anti-phish-regel in PowerShell in of uit te schakelen, schakelt u het hele anti-phishingbeleid (de anti-phish-regel en het toegewezen anti-phish-beleid) in of uit. U kunt het standaardbeleid tegen phishing niet in- of uitschakelen (dit wordt altijd toegepast op alle geadresseerden).

Gebruik de volgende syntaxis om een anti-phish-regel in PowerShell in of uit te schakelen:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de anti-phish-regel met de naam Marketingafdeling uitgeschakeld.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Zie [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Gebruik de volgende syntaxis om de prioriteit van een anti-phish-regel in PowerShell in te stellen:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Opmerkingen**:

- Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-AntiPhishRule.**

- Het standaard anti-phish-beleid heeft geen bijbehorende anti-phish-regel en heeft altijd de onmodifieerbare prioriteit **Laagste.**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid te verwijderen

Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.

Gebruik de volgende syntaxis om een anti-phish-beleid in PowerShell te verwijderen:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het anti-phish-beleid met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Zie [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels te verwijderen

Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.

Gebruik de volgende syntaxis om een anti-phish-regel in PowerShell te verwijderen:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de anti-phish-regel, genaamd Marketingafdeling, verwijderd.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Zie [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga op een van de volgende stappen te werk om te controleren of u anti-phishingbeleid hebt geconfigureerd in Microsoft Defender voor Office 365:

- Ga in het & Compliancecentrum naar  \> **Risicobeheerbeleid** \> **anti-phishing.** Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.** Als u meer details wilt weergeven, gaat u op een van de volgende stappen te werk:

  - Selecteer het beleid in de lijst en bekijk de details in de flyout.
  - Klik **op Standaardbeleid** en bekijk de details in de flyout.

- Vervang in Exchange Online PowerShell de naam van het beleid of de regel, voer de volgende opdracht uit en \<Name\> controleer de instellingen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
