---
title: ATP-beleid tegen phishing configureren
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
description: Beheerders kunnen leren hoe ze de geavanceerde antiphishingbeleidsregels kunnen maken, wijzigen en verwijderen die beschikbaar zijn in organisaties met Office 365 Advanced Threat Protection (ATP).
ms.openlocfilehash: e1a7d3b9d401d8bb5bec08d7b5d58546bbd382aa
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949257"
---
# <a name="configure-atp-anti-phishing-policies"></a>ATP-beleid tegen phishing configureren

ATP-beleid voor phishing maakt deel uit van [Office 365 Advanced Threat Protection.](office-365-atp.md) ATP-beleid tegen phishing kan uw organisatie beschermen tegen schadelijke phishing-aanvallen en andere vormen van phishing-aanvallen. Zie [Anti-phishingbescherming](anti-phishing-protection.md)voor meer informatie over de verschillen tussen antiphishingbeleid in Exchange Online Protection (EOP) en ATP-antiphishingbeleid.

Beheerders kunnen het standaard ATP-antiphishingbeleid bekijken, bewerken en configureren (maar niet verwijderen). Voor meer granulariteit u ook aangepaste ATP-antiphishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U ATP-antiphishingbeleid configureren in het Security & Compliance Center of in Exchange Online PowerShell.

Zie [Antiphishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)voor informatie over het configureren van de beperktere antiphishingbeleidsregels die beschikbaar zijn in Exchange Online Protection-organisaties (dat wil zeggen Office 365-organisaties zonder ATP.

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-exchange-online-powershell"></a>ATP-antiphishingbeleid in het Security & Compliance Center vs Exchange Online PowerShell

De basiselementen van een ATP anti-phishing beleid zijn:

- **Het anti-phish-beleid**: Hiermee geeft u de phishingbeveiligingen op om in te schakelen of uit te schakelen, en de acties om opties toe te passen.

- **De anti-phish-regel**: Geeft de prioriteits- en ontvangerfilters (op wie het beleid van toepassing is) op voor een anti-phish-beleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u ATP-antiphishingbeleid beheert in het Security & Compliance Center:

- Wanneer u een ATP-antiphishingbeleid maakt in het Security & Compliance Center, maakt u eigenlijk een anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd met dezelfde naam voor beide.

- Wanneer u een ATP-antiphishingbeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en wijzigen de filters voor ontvangers de anti-phish-regel. Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.

- Wanneer u een ATP-antiphishingbeleid verwijdert uit het Security & Compliance Center, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.

In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk. U beheert anti-phish-beleid met behulp van de ** \*cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de ** \*cmdlets -AntiPhishRule.**

- In PowerShell maakt u eerst het anti-phish-beleid, vervolgens maakt u de anti-phish-regel die het beleid identificeert waarop de regel van toepassing is.

- In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.

- Wanneer u een anti-phish-beleid uit PowerShell verwijdert, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en vice versa.

### <a name="default-atp-anti-phishing-policy"></a>Standaard ATP anti-phishing beleid

Elke ATP-organisatie heeft een ingebouwd ATP-antiphishingbeleid met de naam Office365 AntiPhish Default met de volgende eigenschappen:

- Het anti-phish-beleid met de naam Office365 AntiPhish Default wordt toegepast op alle ontvangers in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.

- Het beleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laagste** die u niet wijzigen (het beleid wordt altijd als laatste toegepast). Elk aangepast beleid dat u maakt, heeft altijd een hogere prioriteit dan het beleid met de naam Office365 AntiPhish Default.

- Het beleid met de naam Office365 AntiPhish Default is `True`het standaardbeleid (de eigenschap **IsDefault** heeft de waarde) en u het standaardbeleid niet verwijderen.

Om de effectiviteit van anti-phishingbescherming te vergroten, u aangepaste ATP-antiphishingbeleidsregels maken met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik . **ATP anti-phishing** <https://protection.office.com/antiphishing>

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u antiphishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Voor alleen-lezen toegang tot anti-phishingbeleid moet u lid zijn van de rolgroep **Security Reader.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Zie Beleidsinstellingen voor [antiphishing](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)van Office ATP voor onze aanbevolen instellingen voor atp-antiphishing.

- Sta maximaal 30 minuten toe om een nieuw of bijgewerkt beleid toe te passen.

- Zie [Volgorde en voorrang van e-mailbeveiliging in Office 365](how-policies-and-protections-are-combined.md)voor informatie over waar antiphishingbeleid wordt toegepast in de filterpijplijn.

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>Gebruik het Security & Compliance Center om ATP-antiphishingbeleid te maken

Als u een aangepast ATP-antiphishingbeleid maakt in het Security & Compliance Center, wordt de anti-phish-regel en het bijbehorende anti-phish-beleid tegelijkertijd met dezelfde naam voor beide gemaakt.

Wanneer u een ATP-antiphishingbeleid maakt, u alleen de beleidsnaam, beschrijving en het filter voor de ontvanger opgeven dat aangeeft op wie het beleid van toepassing is. Nadat u het beleid hebt gemaakt, u het beleid wijzigen om de standaardinstellingen voor antiphishing te wijzigen of te controleren.

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**

2. Klik op de **antiphishingpagina** op **Maken.**

3. De wizard Een nieuwe wizard **antiphishingbeleid maken** wordt geopend. Configureer op **de pagina Naam van uw beleid** de volgende instellingen:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

   Klik op **Volgende**als u klaar bent.

4. Identificeer **op** de pagina Toegepast op die wordt weergegeven, de interne ontvangers waarop het beleid van toepassing is.

   U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering gebruiken OF-logica (bijv.: _\<afzender1\>_ of _\<afzender2\>_). Verschillende voorwaarden of uitzonderingen gebruiken EN-logica (bijv.: _\<geadresseerde1\>_ en _\<lid van groep 1\>_).

   Klik **op Een voorwaarde toevoegen**. Selecteer in de vervolgkeuzelijst die wordt weergegeven een voorwaarde onder **Toegepast als**:

   - **De ontvanger is:** Hiermee geeft u een of meer postvakken, e-mailgebruikers of e-mailcontactpersonen in uw organisatie op.
   - **De ontvanger is lid van**: Geeft een of meer groepen in uw organisatie op.
   - **Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in Office 365.

   Nadat u de voorwaarde hebt geselecteerd, wordt een overeenkomstige vervolgkeuzelijst weergegeven met een **elk vak.**

   - Klik in het vak en blader door de lijst met waarden die u wilt selecteren.
   - Klik in het vak en begin met typen om de lijst te filteren en een waarde te selecteren.
   - Als u extra waarden wilt toevoegen, klikt u in een leeg gebied in het vak.
   - Als u afzonderlijke vermeldingen **Remove** ![wilt](../../media/scc-remove-icon.png) verwijderen, klikt u op Pictogram Verwijderen op de waarde verwijderen.
   - Als u de hele **Remove** ![voorwaarde](../../media/scc-remove-icon.png) wilt verwijderen, klikt u op Pictogram Verwijderen op voorwaarde.

   Als u een aanvullende voorwaarde wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een resterende waarde onder Toegepast **als**.

   Als u uitzonderingen wilt toevoegen, klikt u op **Een voorwaarde toevoegen** en selecteert u een uitzondering onder Behalve **als**. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

   Klik op **Volgende**als u klaar bent.

5. Controleer op de pagina **Uw instellingen controleren** die wordt weergegeven, uw instellingen. U op **Bewerken** op elke instelling klikken om deze te wijzigen.

   Klik op **Dit beleid maken**als u klaar bent.

6. Klik op **OK** in het bevestigingsdialoogvenster dat wordt weergegeven.

Nadat u het ATP-antiphishingbeleid hebt gemaakt met deze algemene beleidsinstellingen, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>Gebruik het Security & Compliance Center om het ANTI-phishingbeleid van ATP te wijzigen

Gebruik de volgende procedures om het ANTI-phishingbeleid van ATP te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.

1. Als u er nog niet bent, opent u het Beveiligingscentrum & Compliance Center en gaat u naar **Threat Management** \> **Policy** \> **ATP anti-phishing.**

2. Selecteer het aangepaste ATP-antiphishingbeleid dat u wilt wijzigen. Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.

3. De flyout met de naam bewerken van **uw beleid \<\> ** wordt weergegeven. Als u in een sectie op **Bewerken** klikt, hebt u toegang tot de instellingen in die sectie.

   - De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u de secties in elke volgorde selecteren en wijzigen).

   - Nadat u in een sectie op **Bewerken** hebt geklikt, worden de beschikbare instellingen weergegeven in een wizard-indeling, maar u in](../../media/scc-remove-icon.png) elke volgorde binnen de pagina's springen en u op **Opslaan** op een pagina klikken (of pictogram **Annuleren** of **Sluiten** ![sluiten om terug te keren naar de pagina **Uw beleidsnaam \<\> ** bewerken (u hoeft niet de laatste pagina van de wizard te bezoeken om op te slaan of te verlaten).

4. **Beleidsinstelling:** klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u het beleid in de vorige sectie [maakte:](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies)

   - **Naam**
   - **Beschrijving**
   - **Toegepast op**
   - **Uw instellingen controleren**

   Klik op **Opslaan** op een pagina als u klaar bent.

5. **Imitatie**: Klik op **Bewerken** om de beveiligde afzenders en beveiligde domeinen in het beleid te wijzigen. Deze instellingen zijn een voorwaarde voor het beleid dat vervalste afzenders identificeert om te zoeken (individueel of per domein) in het Adres van binnenkomende berichten. Zie [Instellingen voor imitatie in het ANTI-phishingbeleid van ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)voor meer informatie .

   - **Gebruikers toevoegen om te beschermen:** de standaardwaarde is **Uitgeschakeld.** Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**en klikt u op de **knop Gebruiker toevoegen** die wordt weergegeven.

     Configureer in de flyout **van de gebruiker toevoegen** de volgende waarden:

     - **E-mailadres:**

        - Klik in het vak en blader door de lijst met gebruikers om te selecteren.
        - Klik in het vak en begin met typen om de lijst te filteren en een gebruiker te selecteren.
        - Als u een **Remove** ![item wilt](../../media/scc-remove-icon.png) verwijderen, klikt u op Pictogram Verwijderen op de gebruiker.

     - **Naam:** Deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u deze wijzigen.

     Klik op **Opslaan** op een pagina als u klaar bent.

    Als u een bestaand item wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.

   - **Domeinen toevoegen om te beschermen:** Configureer een of beide van de volgende instellingen:

     - **Automatisch de domeinen opnemen die ik bezit:** De standaardwaarde is **Uitgeschakeld.** Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**.
     - **Aangepaste domeinen opnemen:** de standaardwaarde is **Uitgeschakeld**. Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**en voert u in het vak **Domeinen toevoegen** de domeinnaam in (bijvoorbeeld contoso.com), drukt u op ENTER en herhaal t/m indien nodig.

   - **Acties**: Klik op **Bewerken**

     - **Als e-mail wordt verzonden door een nagebootste gebruiker:** Configureer een van de volgende acties voor berichten waarbij de vervalste afzender een van de beveiligde gebruikers is die u hebt opgegeven in **Gebruikers toevoegen om te beschermen:**

       - **Geen actie toepassen**
       - **Bericht doorverwijzen naar andere e-mailadressen**
       - **Bericht verplaatsen naar map Ongewenste e-mail**
       - **Het bericht in quarantaine plaatsen**
       - **Het bericht afgeven en andere adressen toevoegen aan de BCC-regel**
       - **Het bericht verwijderen voordat het wordt bezorgd**

     - **Als e-mail wordt verzonden door een nagebootst domein:** Configureer een van de volgende acties voor berichten waarbij de vervalste afzender zich bevindt in een van de beveiligde domeinen die u hebt opgegeven in **Domeinen toevoegen om te beschermen:**

     - **Geen actie toepassen**
     - **Bericht doorverwijzen naar andere e-mailadressen**
     - **Bericht verplaatsen naar map Ongewenste e-mail**
     - **Het bericht in quarantaine plaatsen**
     - **Het bericht afgeven en andere adressen toevoegen aan de BCC-regel**
     - **Het bericht verwijderen voordat het wordt bezorgd**

   - Klik **op veiligheidstips voor imitatie inschakelen** en configureer een van de volgende instellingen:

     - **Tip weergeven voor geïmiteerde gebruikers:** de standaardwaarde is **uitgeschakeld**. Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**.
     - **Tip weergeven voor nagebootste domeinen:** de standaardwaarde is **Uitgeschakeld.** Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**.
     - **Tip weergeven voor ongebruikelijke tekens:** de standaardwaarde is **Uitgeschakeld**. Als u deze wilt inschakelen, schuift u de schakelaar naar **Aan**.

     Klik op **Opslaan** wanneer u gereed bent.

   - **Postvak intelligentie:**

     - **Postvakintelligentie inschakelen?**: De standaardwaarde is **Ingeschakeld**. Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**

     - **Bescherming voor op postinformatie gebaseerde imitatiebeveiliging inschakelen?**: Deze instelling is alleen beschikbaar als **Postvakintelligentie inschakelen?** is **Ingeschakeld.**

       Als **e-mail wordt verzonden door een nagebootste gebruiker,** u een van de volgende acties opgeven die moeten worden uitgevoerd op berichten die niet voldoen aan postvakinformatie (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):

       - **Geen actie toepassen**
       - **Bericht doorverwijzen naar andere e-mailadressen**
       - **Bericht verplaatsen naar map Ongewenste e-mail**
       - **Het bericht in quarantaine plaatsen**
       - **Het bericht afgeven en andere adressen toevoegen aan de BCC-regel**
       - **Het bericht verwijderen voordat het wordt bezorgd**

   - **Vertrouwde afzenders en domeinen toevoegen:** Geef uitzonderingen op voor het beleid:

     - **Vertrouwde afzenders:**

       - Klik in het vak en blader door de lijst met gebruikers om te selecteren.
       - Klik in het vak en begin met typen om de lijst te filteren en een gebruiker te selecteren.
       - Als u een **Remove** ![item wilt](../../media/scc-remove-icon.png) verwijderen, klikt u op Pictogram Verwijderen op de gebruiker.

     - **Vertrouwde domeinen**: Voer de domeinnaam in (bijvoorbeeld contoso.com), druk op ENTER en herhaal indien nodig.

   - **Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.

     - U in elke sectie op **Bewerken** klikken om terug te gaan naar de desbetreffende pagina.
     - U de volgende instellingen direct op deze pagina **in-** of **uitschakelen:**

       - **Beveiligde gebruikers**
       - **Beveiligde domeinen** \> **Domeinen Omvatten domeinen die ik bezit**
       - **Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)
       - **Postvakintelligentie**

   Klik op **Opslaan** op een pagina als u klaar bent.

6. **Spoof:** klik op **Bewerken** om spoofinformatie in- of uit te schakelen, de identificatie van niet-geverifieerde afzenders in Outlook in of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders. Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie.

   Houd er rekening mee dat dezelfde instellingen ook beschikbaar zijn in anti-phishingbeleid in EOP.

   - **Instellingen voor spoofingfilters:** de standaardwaarde is **ingeschakeld**en we raden u aan deze aan te laten staan. Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.** Zie [spoof-intelligentie configureren in Office 365](learn-about-spoof-intelligence.md) voor meer informatie.

     > [!NOTE]
     > U hoeft anti-spoofingbeveiliging niet uit te schakelen als uw MX-record niet naar Office 365 wijst. u schakelt in plaats daarvan Uitgebreide filtering voor connectors in. Zie Uitgebreide [filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)instructies .

   - **Functie Niet-geverifieerde afzender inschakelen:** de standaardwaarde is **Ingeschakeld**. Als u deze wilt uitschakelen, schuift u de schakelaar naar **Uit.**

   - **Acties:** Geef de actie op die moet worden uitgevoerd met berichten die niet in de spoofinformatie zijn geslaagd:

     **Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen:**

     - **Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden**
     - **Het bericht in quarantaine plaatsen**

   - **Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.

     - U in elke sectie op **Bewerken** klikken om terug te gaan naar de desbetreffende pagina.
     - U de volgende instellingen direct op deze pagina **in-** of **uitschakelen:**

       - **Antispoofing-beveiliging inschakelen**
       - **Functie Niet-geverifieerde afzender inschakelen**

   Klik op **Opslaan** op een pagina als u klaar bent.

7. **Geavanceerde instellingen:** Klik op **Bewerken** om de geavanceerde phishingdrempels te configureren. Zie [Geavanceerde phishingdrempels in het ATP-beleid voor phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)voor meer informatie.

   - **Geavanceerde phishingdrempels:** Selecteer een van de volgende waarden:

   - **1 - Standaard** (dit is de standaardwaarde.)
   - **2 - Agressief**
   - **3 - Agressiever**
   - **4 - Meest agressieve**

   - **Uw instellingen controleren:** klik op **Bewerken** om terug te gaan naar de pagina **Geavanceerde phishingdrempels.**

   Klik op Opslaan op **een** van beide pagina's als u klaar bent.

8. Terug op de pagina **Uw beleidsnaam \<\> bewerken,** uw instellingen controleren en vervolgens op **Sluiten**klikken.

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>Gebruik het Beveiligings- & Compliance Center om het standaard BELEID voor ANTI-phishing van ATP te wijzigen

Het standaard BELEID voor antiphishing van ATP heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels. Ga als volgt te werk om het standaard BELEID voor ANTI-phishing van ATP te wijzigen:

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**

2. Klik op de pagina **Anti-phishing** op **Standaardbeleid**.

3. De pagina **Standaardinstelling voor uw beleid Office365 AntiPhish** wordt weergegeven. De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt:](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies)

   - **Imitatie**
   - **Spoof**
   - **Geavanceerde instellingen**

   De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:

   - U de sectie **Beleidsinstelling** en waarden zien, maar er is geen **koppeling Bewerken,** dus u de instellingen (beleidsnaam, beschrijving en op wie het beleid van toepassing is op niet wijzigen (het is van toepassing op alle ontvangers)).
   - U het standaardbeleid niet verwijderen.
   - U de prioriteit van het standaardbeleid niet wijzigen (het wordt altijd als laatste toegepast).

4. Controleer op de pagina **Standaardbeleid Office365 AntiPhish bewerken** uw instellingen en klik op **Sluiten**.

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>Aangepaste ATP-antiphishingbeleidsregels in- of uitschakelen

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**

2. Let op de waarde in de kolom **Status:**

   - Schuif de schakel naar **Uit** om het beleid uit te schakelen.

   - Schuif de schakelaar naar **Aan** om het beleid in te schakelen.

U het standaard antiphishingbeleid niet uitschakelen.

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>De prioriteit instellen van aangepast ATP-antiphishingbeleid

Standaard krijgt het ATP-antiphishingbeleid een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwer beleid heeft een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.

Aangepaste ATP-antiphishingbeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0). Het standaard antiphishingbeleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laagste**en u deze niet wijzigen.

 **Opmerking:** In het Security & Compliance Center u de prioriteit van het ATP-antiphishingbeleid alleen wijzigen nadat u het hebt gemaakt. In PowerShell u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).

Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u het **prioriteitsnummer** niet rechtstreeks wijzigen in het Beveiligings& Compliance Center). Het wijzigen van de prioriteit van een beleid heeft alleen zin als u meerdere beleidsregels hebt.

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**

2. Selecteer het beleid dat u wilt wijzigen. Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.

3. De flyout met de naam bewerken van **uw beleid \<\> ** wordt weergegeven.

   - Het aangepaste ATP-antiphishingbeleid met de **prioriteitswaarde** **0** heeft alleen de **knop Prioriteit verlagen** beschikbaar.

   - Het aangepaste ATP-antiphishingbeleid met de laagste **prioriteitswaarde** (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.

   - Als u drie of meer aangepaste antiphishingbeleidsregels hebt, hebben beleidsregels tussen de hoogste en laagste prioriteitswaarden zowel de **prioriteitsprioriteit verhogen** als **Prioriteitsknoppen verlagen** beschikbaar.

4. Klik **op Prioriteit verhogen** of Prioriteit **verlagen** om de **prioriteitswaarde te** wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>Gebruik het Beveiligingscentrum & Compliance Center om het ANTI-phishingbeleid van ATP weer te geven

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**

2. Een van de volgende stappen uitvoeren:

   - Selecteer een aangepast ATP-antiphishingbeleid dat u wilt weergeven. Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.

   - Klik **op Standaardbeleid** om het standaard beleid voor antiphishing weer te geven.

3. De flyout met de naam bewerken van **uw beleid \<\> ** wordt weergegeven, waar u de instellingen en waarden bekijken.

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>Gebruik het Beveiligings- & Compliance Center om het ANTI-phishingbeleid van ATP te verwijderen

1. Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.**

2. Selecteer het beleid dat u wilt verwijderen. Als deze al is geselecteerd, schakelt u de selectie uit en selecteert u deze opnieuw.

3. Klik in de flyout **van de beleidsnaam \<\> bewerken** die wordt weergegeven op Beleid **verwijderen**en klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>Exchange Online PowerShell gebruiken om ATP-antiphishingbeleid te configureren

### <a name="use-powershell-to-create-anti-phishing-policies"></a>PowerShell gebruiken om antiphishingbeleid te maken

Het maken van een anti-phishing beleid in PowerShell is een proces in twee stappen:

1. Maak het anti-phish-beleid.

2. Maak de anti-phish-regel die het anti-phish-beleid aangeeft waarop de regel van toepassing is.

 **Opmerkingen**:

- U een nieuwe anti-phish-regel maken en er een bestaand, niet-geassocieerd anti-phish-beleid aan toewijzen. Een anti-phish regel kan niet worden geassocieerd met meer dan een anti-phish beleid.

- U de volgende instellingen configureren voor nieuwe anti-phish-beleidsregels in PowerShell die pas beschikbaar zijn in het Security & Compliance Center nadat u het beleid hebt gemaakt:

  - Het nieuwe beleid als uitgeschakeld maken _(ingeschakeld_ `$false` op de cmdlet **Nieuw-AntiPhishRule).**

  - Stel de prioriteit in van het beleid tijdens het maken ( _ \<Prioriteitsnummer\>_) op de cmdlet **Nieuw-AntiPhishRule.** _Priority_

- Een nieuw anti-phish-beleid dat u in PowerShell maakt, is niet zichtbaar in het Security & Compliance Center totdat u het beleid toewijst aan een anti-phish-regel.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Stap 1: PowerShell gebruiken om een anti-phish-beleid te maken

Als u een anti-phish-beleid wilt maken, gebruikt u de als volgt:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In dit voorbeeld wordt anti-phish-beleid met de naam Research Quarantine met de volgende instellingen gemaakt:

- Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet `$true`en de standaardwaarde is ).
- De beschrijving is: Het beleid van de afdeling van het onderzoek.
- Hiermee u organisatiedomeinen beveiliging voor alle geaccepteerde domeinen en gerichte domeinenbescherming voor fabrikam.com.
- Hiermee geeft u Mai Fujito (mfujito@fabrikam.com) op als de gebruiker om te beschermen tegen imitatie.
- Hiermee schakelt u postvakintelligentie in.
- Hiermee schakelt u de beveiliging van postvakintelligentie in en geeft u de quarantaineactie op.
- Hiermee kunnen veiligheidstips worden gegeven.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Zie [Nieuw-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Stap 2: PowerShell gebruiken om een anti-phish-regel te maken

Als u een anti-phish-regel wilt maken, gebruikt u de als volgt:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een anti-phish-regel met de naam Research Department met de volgende voorwaarden gemaakt:

- De regel is gekoppeld aan het anti-phish-beleid met de naam Research Quarantine.
- De regel is van toepassing op leden van de groep met de naam Research Department.
- Omdat we de parameter _Prioriteit_ niet gebruiken, wordt de standaardprioriteit gebruikt.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Zie [Nieuw-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid weer te geven

Als u bestaande anti-phish-beleidsregels wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst geretourneerd van alle anti-phish-beleidsregels, samen met de opgegeven eigenschappen.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In dit voorbeeld worden alle eigenschapswaarden voor het anti-phish-beleid met de naam Leidinggevenden geretourneerd.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Zie [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels weer te geven

Als u bestaande anti-phish-regels wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In dit voorbeeld wordt een overzichtslijst met alle anti-phish-regels geretourneerd, samen met de opgegeven eigenschappen.

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

In dit voorbeeld worden alle eigenschapswaarden voor de anti-phish-regel met de naam Contoso Executives geretourneerd.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Zie [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid te wijzigen

Anders dan de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit onderwerp een sectie [anti-phish-beleid te maken.](#step-1-use-powershell-to-create-an-anti-phish-policy)

- De _Switch MakeDefault_ die het opgegeven beleid inschakelt in het standaardbeleid (toegepast op iedereen, altijd **laagste** prioriteit en u het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt.

- U de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _parameter Naam)._ Wanneer u de naam van een antiphishingbeleid wijzigt in het Security & Compliance _rule_Center, wijzigt u alleen de anti-phish-regel.

Als u een anti-phish-beleid wilt wijzigen, gebruikt u de als volgt:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-AntiPhishPolicy voor](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken. Zie de volgende sectie om bestaande anti-phish-regels in te schakelen of uit te schakelen.

Anders zijn er geen aanvullende instellingen beschikbaar wanneer u een anti-phish-regel in PowerShell wijzigt. Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een sectie anti-phish-regel te maken.](#step-2-use-powershell-to-create-an-anti-phish-rule)

Als u een anti-phish-regel wilt wijzigen, gebruikt u de als volgt:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Zie [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule)voor gedetailleerde syntaxis- en parameterinformatie .

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels in te schakelen of uit te schakelen

Het in- of uitschakelen van een anti-phish-regel in PowerShell schakelt of schakelt het hele anti-phishingbeleid in of uit (de anti-phish-regel en het toegewezen anti-phish-beleid). U het standaard beleid voor antiphishing niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).

Gebruik de als volgt te houden of een anti-phish-regel in PowerShell in te schakelen:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de anti-phish-regel met de naam MarketingAfdeling uitgeschakeld.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Zie [Inschakelen-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) en [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>PowerShell gebruiken om de prioriteit van anti-phish-regels in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit van een anti-phish-regel in PowerShell wilt instellen, gebruikt u de volgende syntaxis:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Opmerkingen**:

- Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **Nieuw-AntiPhishRule.**

- Het standaard anti-phish-beleid heeft geen overeenkomstige anti-phish-regel en heeft altijd de onaanpasbare prioriteitswaarde **Laagste**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>PowerShell gebruiken om anti-phish-beleid te verwijderen

Wanneer u PowerShell gebruikt om een anti-phish-beleid te verwijderen, wordt de bijbehorende anti-phish-regel niet verwijderd.

Als u een anti-phish-beleid in PowerShell wilt verwijderen, gebruikt u de als volgt:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het anti-phish-beleid met de naam Marketing Department verwijderd.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Zie [Verwijderen-antiphishbeleid voor](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy)gedetailleerde syntaxis- en parameterinformatie .

### <a name="use-powershell-to-remove-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels te verwijderen

Wanneer u PowerShell gebruikt om een anti-phish-regel te verwijderen, wordt het bijbehorende anti-phish-beleid niet verwijderd.

Als u een anti-phish-regel in PowerShell wilt verwijderen, gebruikt u de als volgt:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de anti-phish-regel met de naam MarketingAfdeling verwijderd.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Zie [Verwijderen-antiphishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

Ga een van de volgende stappen uit om te controleren of u het ANTI-phishingbeleid van ATP hebt geconfigureerd:

- Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **ATP anti-phishing.** Controleer de lijst met beleidsregels, hun **statuswaarden** en hun **prioriteitswaarden.** Ga als volgt te werk om meer details te bekijken:

  - Selecteer het beleid in de lijst en bekijk de details in de flyout.
  - Klik **op Standaardbeleid** en bekijk de details in de flyout.

- Vervang in \<Exchange Online\> PowerShell Naam door de naam van het beleid of de regel en voer de volgende opdracht uit en controleer de instellingen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
