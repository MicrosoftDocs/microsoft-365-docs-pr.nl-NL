---
title: ATP-beleid tegen phishing configureren
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
description: Beheerders kunnen leren hoe u het geavanceerde anti-phishingfilter kunt maken, wijzigen en verwijderen, dat beschikbaar is in organisaties met Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 2986102b549b7302a7a4ac533f80846d832aeb41
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328069"
---
# <a name="configure-atp-anti-phishing-policies"></a>ATP-beleid tegen phishing configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


ATP anti-Phishingfilter maakt deel uit van [Office 365 Advanced Threat Protection](office-365-atp.md). Met een anti-phishingfilter van ATP kunt u uw organisatie beschermen tegen kwaadaardige aanvallen op basis van kwaadaardige gebruikers en andere typen phishing-aanvallen. Zie [bescherming tegen phishing](anti-phishing-protection.md)voor meer informatie over de verschillen tussen het anti-virus beleid in Exchange Online Protection (EOP) en het ATP anti phishingfilter.

Beheerders kunnen het standaardbeleid voor de vrije voor uitphishing van vrije gebruikers weergeven, bewerken en configureren (maar niet verwijderen). Voor een grotere nauwkeurigheid kunt u ook aangepast ATP anti-phishingfilter maken dat geldt voor specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U kunt het beleid voor het instellen van ATP anti phishing configureren in de beveiligings & nalevings centrum of in Exchange Online PowerShell.

Zie [anti phishingberichten configureren in EOP](configure-anti-phishing-policies-eop.md)voor informatie over het configureren van het meer beperkte beveiligingsbeleid dat beschikbaar is in Exchange Online Protection-organisaties (dat wil zeggen microsoft 365-organisaties zonder Office 365 ATP).

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a>ATP anti-phishingfilter in de beveiligings & nalevings centrum VS PowerShell

De basiselementen van een ATP anti-phishingfilter zijn:

- **Het anti-virus beleid**: Hiermee geeft u de phishing-beveiliging op om in of uit te schakelen, en de acties voor het toepassen van opties.
- **De anti-phishings regel**: Hiermee geeft u de prioriteiten en de filters voor geadresseerden op (wie het beleid van toepassing is) voor een anti-phishing beleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u het beleid voor het beheren van ATP anti-phishing beheert in het beveiligings & nalevings centrum:

- Wanneer u een beleid maakt, maakt u eigenlijk een anti-phishings regel en het bijbehorende anti-phishings beleid met dezelfde naam voor beide.
- Wanneer u een beleid wijzigt, worden de instellingen voor de naam, prioriteit, ingeschakeld of uitgeschakeld en de filters voor geadresseerden de anti-late regel gewijzigd. Alle andere instellingen wijzigen het bijbehorende anti-phishings beleid.
- Wanneer u een beleid verwijdert, worden de anti-phishings regel en het bijbehorende anti-onphishings beleid verwijderd.

In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk. Zie voor meer informatie de sectie [Exchange Online PowerShell gebruiken voor het configureren van het onderdeel ATP anti-phishingfilter](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) in dit onderwerp.

Elke Office 365 ATP-organisatie heeft een ingebouwde ATP anti-phishingfilter met de naam Office365 AntiPhish standaard met de volgende eigenschappen:

- Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-avond regel (Recipient filters) gekoppeld aan het beleid.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Om de effectiviteit van bescherming tegen phishing te bevorderen, kunt u aangepaste ATP anti-phishingfilter-beleidsregels maken met strikte instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u direct naar de pagina voor het gebruik van **ATP anti phishing** wilt gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

- U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:

  - Als u een beleid wilt toevoegen, wijzigen of verwijderen uit het beleid van ATP, moet u lid zijn van een van de volgende rollen groepen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezen toegang tot ATP anti-phishingfilter moet u lid zijn van een van de volgende rollen groepen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Voor de aanbevolen instellingen voor het anti-phishingfilter van ATP, raadpleegt u de [instellingen van het beleid voor het anti-phishingfilter van ATP](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).

- Maximaal 30 minuten toegestaan voor het toepassen van een nieuwe of bijgewerkte beleidsregels.

- Zie de [volgorde en prioriteit van e-mail beveiliging](how-policies-and-protections-are-combined.md)voor informatie over waar anti phishingfilter in de filter pijplijn wordt toegepast.

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a>De beveiligings & voor compliance gebruiken om een ATP anti-phishings beleid te maken

Wanneer u een aangepast ATP anti-Phishingfilter maakt in het compliance-& Beveiligingscentrum, maakt de anti-phishings regel en het bijbehorende anti-phishings beleid op hetzelfde moment op dezelfde manier met dezelfde naam voor beide.

Wanneer u een ATP anti-Phishingfilter maakt, kunt u alleen de Beleidsnaam, de beschrijving en het filter voor de ontvanger opgeven waarmee wordt aangegeven voor wie het beleid van toepassing is. Nadat u het beleid hebt gemaakt, kunt u het beleid wijzigen, zodat u de standaardinstellingen voor anti phishing kunt wijzigen of bekijken.

1. Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.

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
   - **Het domein van de ontvanger is**: geeft de geadresseerden op in een of meer van de geconfigureerde domeinen in de organisatie.

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

Nadat u het ATP anti-phishingfilter met deze algemene beleidsinstellingen hebt gemaakt, volgt u de instructies in het volgende gedeelte om de beveiligingsinstellingen in het beleid te configureren.

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a>U kunt het nalevings centrum voor beveiligings & gebruiken om het gebruik van ATP anti-phishing-beleid te wijzigen

Gebruik de volgende procedures voor het wijzigen van het gebruik van ATP anti-Phishingfilter: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.

1. Als u dit nog niet hebt gedaan, opent u het beveiligings & nalevings centrum en gaat u naar het beleid voor het beleid voor **bedreigings beheer** voor \> **Policy** \> **ATP anti phishing**.

2. Selecteer het aangepaste ATP anti phishing-beleid dat u wilt wijzigen. Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.

3. De flyout **uw beleid \<name\> bewerken** wordt weergegeven. Als u in een sectie op **bewerken** klikt, krijgt u toegang tot de instellingen in deze sectie.

   - De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in een willekeurige volgorde selecteren en wijzigen).

   - Nadat u op **bewerken** in een sectie hebt geklikt, worden de beschikbare instellingen in de wizard indeling weergegeven, maar u kunt wel binnen de pagina's in een willekeurige Volg **Cancel** orde springen **Close** , en u kunt op de pagina **Opslaan** of sluiten klikken op het pictogram voor het ![ ](../../media/scc-remove-icon.png) **bewerken van uw beleid \<name\> ** (u hoeft niet te klikken op de laatste pagina van de wizard om de pagina te openen

4. **Beleidsinstelling**: Klik op **bewerken** als u de instellingen wilt wijzigen die beschikbaar waren wanneer u [het beleid hebt gemaakt](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in de vorige sectie:

   - **Naam**
   - **Beschrijving**
   - **Toegepast op**
   - **De instellingen bekijken**

   Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.

5. **Imitatie**: Klik op **bewerken** om de beveiligde afzenders en beveiligde domeinen in het beleid te wijzigen. Deze instellingen vormen een voorwaarde voor het beleid waarmee vervalste afzenders worden geïdentificeerd om te zoeken naar (afzonderlijk of per domein) in het van-adres van inkomende berichten. Zie voor meer informatie [imitatie-instellingen in het anti-phishingfilter-beleid](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).

   - **Gebruikers toevoegen om te beveiligen**: de standaardwaarde is **uitgeschakeld**. Als u de functie wilt inschakelen, verschuift u de schuifregelaar naar **aan**en klikt u op de knop **gebruiker toevoegen** die wordt weergegeven.

     Configureer de volgende waarden in het vervolgmenu **gebruiker toevoegen** dat wordt weergegeven:

     - **E-mailadres**:

        - Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.
        - Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.
        - Als u een vermelding **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de gebruiker.

     - **Naam**: deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u kunt dit wijzigen.

     Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.

    Als u een bestaande vermelding wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.

   - **Domeinen toevoegen die u wilt beveiligen**: Configureer een of beide van de volgende instellingen:

     - **Automatisch de domeinen opnemen waarvan ik de eigenaar ben**: de standaardwaarde is **uitgeschakeld**. Schuif de wisselknop **naar aan om**deze optie in te schakelen.
     - **Aangepaste domeinen opnemen**: de standaardwaarde is **uitgeschakeld**. Als u deze optie wilt inschakelen, verschuift u de schuifregelaar naar **aan**en voert u in het vak **domeinen toevoegen** de domeinnaam in (bijvoorbeeld contoso.com), drukt u op ENTER en herhaalt u de gewenste stappen.

   - **Acties**: Klik op **bewerken**

     - **Als e-mail wordt verzonden door een geïmiteerde gebruiker**: Configureer een van de volgende acties voor berichten waarbij de vervalste afzender een van de beveiligde gebruikers is die u hebt opgegeven in de **gebruikers toevoegen om te beschermen**:

       - **Geen actie toepassen**
       - **Bericht omleiden naar andere e-mailadressen**
       - **Bericht verplaatsen naar map Ongewenste e-mail**
       - **Het bericht Quarantine**
       - **Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**
       - **Het bericht verwijderen voordat het wordt bezorgd**

     - **Als e-mailberichten worden verzonden door een geïmiteerd domein**: Configureer een van de volgende acties voor berichten waarvan de vervalste verzender zich bevindt in een van de beveiligde domeinen die u hebt opgegeven in **domeinen toevoegen om te beschermen**:

     - **Geen actie toepassen**
     - **Bericht omleiden naar andere e-mailadressen**
     - **Bericht verplaatsen naar map Ongewenste e-mail**
     - **Het bericht Quarantine**
     - **Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**
     - **Het bericht verwijderen voordat het wordt bezorgd**

   - Klik op de **beveiligingstips voor imitatie inschakelen** en configureer de volgende instellingen:

     - **Tip weergeven voor geïmiteerde gebruikers**: de standaardwaarde is **uitgeschakeld**. Schuif de wisselknop **naar aan om**deze optie in te schakelen.
     - **Tip weergeven voor geïmiteerde domeinen**: de standaardwaarde is **uitgeschakeld**. Schuif de wisselknop **naar aan om**deze optie in te schakelen.
     - **Tip voor ongebruikelijk tekens weergeven**: de standaardwaarde is **uitgeschakeld**. Schuif de wisselknop **naar aan om**deze optie in te schakelen.

     Klik op **Opslaan** wanneer u gereed bent.

   - **Postvak informatie**:

     - **Postvak intelligentie inschakelen?**: de standaardwaarde is **ingeschakeld**. Verschuif de wissel **knop om deze**uit te schakelen.

     - **Schakelt u de bescherming van imitatie op basis van een postvak in?**: deze instelling is alleen beschikbaar als **Postvak Intelligence inschakelen?** is **ingeschakeld**.

       In **als e-mailbericht wordt verzonden door een geïmiteerde gebruiker**, kunt u een van de volgende acties opgeven voor het uitvoeren van berichten die niet beschikbaar zijn voor de Postvak informatie (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):

       - **Geen actie toepassen**
       - **Bericht omleiden naar andere e-mailadressen**
       - **Bericht verplaatsen naar map Ongewenste e-mail**
       - **Het bericht Quarantine**
       - **Het bericht bezorgen en andere adressen toevoegen aan de regel BCC**
       - **Het bericht verwijderen voordat het wordt bezorgd**

   - **Vertrouwde afzenders en domeinen toevoegen**: Geef uitzonderingen voor het beleid op:

     - **Vertrouwde afzenders**:

       - Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.
       - Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.
       - Als u een vermelding **wilt verwijderen, klikt u** op ![ het pictogram verwijderen ](../../media/scc-remove-icon.png) van de gebruiker.

     - **Vertrouwde domeinen**: Voer de domeinnaam in (bijvoorbeeld contoso.com), druk op ENTER en herhaal de gewenste stappen.

   - **Controleer uw instellingen**: in plaats van op elke afzonderlijke stap te klikken, worden de instellingen in een overzicht weergegeven.

     - U kunt in elke sectie op **bewerken** klikken om terug te gaan naar de gewenste pagina.
     - U kunt de volgende instellingen rechtstreeks op deze pagina **in** -of **uitschakelen** :

       - **Beveiligde gebruikers**
       - **Beveiligde domeinen** \> **Ook domeinen opnemen waarvan ik eigenaar ben**
       - **Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)
       - **Postvak intelligentie**

   Wanneer u klaar bent, klikt u op **Opslaan** op een willekeurige pagina.

6. **Spoof**: Klik op **bewerken** als u de identiteit van spoofing wilt in-of uitschakelen, schakel de identificatie van niet-geverifieerde afzenders in Outlook in of uit en configureer de actie die u wilt toepassen op berichten van geblokkeerde vervalste afzenders. Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md#spoof-settings).

   Deze instellingen zijn ook beschikbaar in het anti-phishings beleid in EOP.

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

7. **Geavanceerde instellingen**: Klik op **bewerken** om de drempelwaarden voor Geavanceerd phishing te configureren. Zie voor meer informatie [Geavanceerde phishingberichten in het anti-phishingfilter-beleid](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).

   - **Geavanceerde fraude drempels**: Selecteer een van de volgende waarden:

   - **1-standaard** (dit is de standaardwaarde.)
   - **2-agressief**
   - **3-meer agressief**
   - **4-de scherpste**

   - **Controleer uw instellingen**: Klik op **bewerken** om terug te gaan naar de pagina Geavanceerde instellingen voor **phishing** .

   Wanneer u klaar bent, klikt u op **Opslaan** op een van beide pagina's.

8. Ga op de pagina ** \<Name\> beleid bewerken** naar de instellingen en klik op **sluiten**.

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a>Met behulp van het compliance-beveiligings & u het standaardbeleid voor het anti-phishingfilter van ATP

Het standaard-Phishingfilter anti-phishingfilter heeft de naam Office365 AntiPhish standaard en wordt niet weergegeven in de lijst met beleidsregels. Voer de volgende stappen uit als u het standaard-Phishingfilter voor de vrije tijd wilt wijzigen:

1. Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.

2. Klik op de pagina **anti phishing** op **standaardbeleid**.

3. De standaardpagina voor het **bewerken van uw beleid Office365 AntiPhish** wordt weergegeven. De volgende secties zijn beschikbaar, met een identieke instelling voor [het wijzigen van een aangepast beleid](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):

   - **Imitatie**
   - **Met**
   - **Geavanceerde instellingen**

   De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:

   - U ziet de secties en waarden van de **beleidsinstelling** , maar er is geen koppeling voor **bewerken** , zodat u de instellingen (Beleidsnaam en beschrijving, en wie het beleid van toepassing is op alle geadresseerden), niet kunt wijzigen.
   - U kunt het standaardbeleid niet verwijderen.
   - Het is niet mogelijk om de prioriteit van het standaardbeleid te wijzigen (dit wordt altijd als laatste toegepast).

4. Controleer de instellingen op de pagina **uw beleid Office365 AntiPhish standaard** instellen en klik op **sluiten**.

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a>Aangepaste ATP anti-phishings beleid in-of uitschakelen

1. Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.

2. Let op de waarde in de kolom **status** :

   - Schuif de wisselknop naar **uit** om het beleid uit te schakelen.

   - Schuif de wisselknop naar **aan om het beleid in te** schakelen.

U kunt het standaard anti-Phishingfilter niet uitschakelen.

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a>De prioriteit van een aangepast ATP anti-phishings beleid instellen

Standaard krijgt u in het geval van een anti-phishingfilter een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels zijn een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Aangepast ATP anti-phishingfilter worden weergegeven in de volgorde waarin ze zijn verwerkt (het eerste beleid heeft **de waarde 0** ). Het standaard anti-phishingfilter met de naam Office365 AntiPhish standaard heeft de waarde van een aangepaste **prioriteit en kunt**deze niet wijzigen.

 **Opmerking**: in het beveiligings & nalevings centrum kunt u alleen de prioriteit van het anti-phishingfilter wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit negeren wanneer u de regel voor de anti-phishing maakt (die van invloed kunnen zijn op de prioriteit van bestaande regels).

Als u de prioriteit van een beleid wilt wijzigen, klikt u op **prioriteit verhogen** of **prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **prioriteits** nummer niet rechtstreeks wijzigen in de beveiligings & compliance Center). Als u meerdere beleidsregels hebt, kunt u de prioriteit van een beleid alleen wijzigen.

1. Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.

2. Selecteer het beleid dat u wilt wijzigen. Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.

3. De flyout **uw beleid \<name\> bewerken** wordt weergegeven.

   - Het aangepaste ATP anti-phishingfilter met de **prioriteits** waarde **0** heeft slechts de knop **prioriteit verlagen** .

   - Het aangepaste ATP anti-phishingfilter met de laagste **prioriteits** waarde (bijvoorbeeld **3**) is slechts de knop **prioriteit verhogen** beschikbaar.

   - Als u beschikt over drie of meer aangepaste anti phishingfilter-beleidsregels, hebben beleidsregels tussen de hoogste en laagste prioriteit de knoppen **prioriteit verhogen** en **prioriteit verlagen** .

4. Klik op **prioriteit verhogen** of **prioriteit verkleinen** om de **prioriteits** waarde te wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a>Met behulp van het beveiligings & compliance

1. Ga in het beveiligings & compliance Center naar het beleid voor het beheer van bedreigingen en ga naar het beleid voor het **beheer van bedreigingen** \> **Policy** \> **ATP anti-phishing**.

2. Voer een van de volgende stappen uit:

   - Selecteer een aangepast ATP anti phishing-beleid dat u wilt bekijken. Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.

   - Klik op **standaardbeleid** om het standaard anti-phishingfilter te bekijken.

3. De flyout voor het **beleid \<name\> bewerken** wordt weergegeven, waarin u de instellingen en waarden kunt weergeven.

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a>Met behulp van het beveiligings & compliance

1. Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**.

2. Selecteer het beleid dat u wilt verwijderen. Als de optie al is geselecteerd, schakelt u deze uit en selecteert u het opnieuw.

3. Klik in het vervolgmenu **uw beleidsregels \<name\> bewerken** dat wordt weergegeven op **beleid verwijderen**en klik vervolgens op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a>PowerShell van Exchange Online gebruiken om een anti-phishings beleid van ATP te configureren

Zoals hierboven beschreven, bestaat een anti-spam beleid en een anti-phishings regel.

In Exchange Online PowerShell is het verschil tussen anti-malwarebeleid en anti-phishing regels zichtbaar. U een anti-phishings beleid beheert met behulp van de cmdlets ** \* AntiPhishPolicy** en u beheert de anti-phishings regels met behulp van de cmdlets voor ** \* AntiPhishRule** .

- In PowerShell maakt u eerst het anti-phishings beleid en vervolgens maakt u een anti-phishings regel waarmee het beleid wordt aangegeven waarop de regel van toepassing is.
- In PowerShell wijzigt u de instellingen van het anti-phishings beleid en de anti-phishing regel afzonderlijk.
- Wanneer u een anti-phishings beleid verwijdert uit PowerShell, wordt de overeenkomstige anti-phishing regel niet automatisch verwijderd en vice versa.

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
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In dit voorbeeld wordt een anti-phishings beleid met de naam onderzoek quarantaine gemaakt met de volgende instellingen:

- Het beleid is ingeschakeld (de parameter _enabled_ wordt niet gebruikt en de standaardwaarde is `$true` ).
- De beschrijving luidt: afdelings beleid voor onderzoek.
- Schakelt de bescherming van organisatie domeinen in voor alle geaccepteerde domeinen en gerichte domeinbeveiliging voor fabrikam.com.
- Hiermee wordt Mai Fujito (mfujito@fabrikam.com) opgegeven als de gebruiker die de gebruiker wil beschermen tegen onbevoegden.
- Schakelt postvak informatie in.
- Schakelt de functie voor Postvak beveiliging in en geeft de quarantaine actie aan.
- Maakt veiligheidstips.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
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

Met uitzondering van de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phishings beleid in PowerShell aanpast wanneer u het beleid maakt zoals wordt beschreven in de sectie [stap 1: gebruik PowerShell om een anti-phishings sectie te maken](#step-1-use-powershell-to-create-an-anti-phish-policy) eerder in dit onderwerp.

- De schakeloptie _MakeDefault_ waarmee het opgegeven beleid wordt omgezet in het standaardbeleid (voor iedereen, de **laagste** prioriteit en het niet verwijderen) is alleen beschikbaar wanneer u een anti-Echobeleid wijzigt in PowerShell.

- U kunt niet de naam van een anti-phishings beleid wijzigen (de cmdlet **set-AntiPhishPolicy** heeft geen _naam_ parameter). Wanneer u de naam van een anti-phishingfilter wijzigt in de beveiligings & nalevings centrum, kunt u de naam van de anti-phishing _regel_alleen wijzigen.

Voor het wijzigen van een anti-phishings beleid gebruikt u de volgende syntaxis:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Zie [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell gebruiken om anti-phishings regels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een anti-phishings regel wijzigt in PowerShell is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande anti-Phish regels wilt in-of uitschakelen.

Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phishing regel wijzigt in PowerShell. U kunt dezelfde instellingen gebruiken wanneer u een regel maakt zoals wordt beschreven in [stap 2: PowerShell gebruiken om een anti-phishings sectie te maken](#step-2-use-powershell-to-create-an-anti-phish-rule) eerder in dit onderwerp.

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

- Ga in het beveiligings & compliance naar het compliance-beleid voor het **beheer** van behulp van een \> **Policy** \> **anti-phishing**. Controleer de lijst met beleidsregels, de **status** waarden en de waarden van de **prioriteit** . Ga op een van de volgende manieren te werk om meer informatie weer te geven:

  - Selecteer een beleid in de lijst en Bekijk de details in de vervolgkeuzelijst.
  - Klik op **standaardbeleid** en Bekijk de details in het vervolgmenu.

- In Exchange Online PowerShell vervangt u \<Name\> de naam van het beleid of de regel en voert u de volgende opdracht uit en controleert u de instellingen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
