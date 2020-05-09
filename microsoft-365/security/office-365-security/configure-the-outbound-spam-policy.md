---
title: Filteren van uitgaande spam configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over het configureren van uitgaand spambeleid dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie.
ms.openlocfilehash: efd3fecc2447435f40e4e20fd958e8f3b2d8e48f
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173438"
---
# <a name="configure-outbound-spam-filtering"></a>Filteren van uitgaande spam configureren

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection(EOP)-klant zonder Exchange Online-postvakken, worden uitgaande e-mailberichten die via EOP worden verzonden, automatisch gecontroleerd op spam en ongebruikelijke verzendactiviteiten.

Uitgaande spam van een gebruiker in uw organisatie duidt doorgaans op een gecompromitteerd account. Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het spamvertrouwensniveau of SCL) en worden door de risicogroep geleid om de reputatie van de service te beschermen (dat wil zeggen, houd Microsoft 365 brone-mailservers van [IP-bloklijsten](high-risk-delivery-pool-for-outbound-messages.md) af). Beheerders worden automatisch op de hoogte gesteld van verdachte uitgaande e-mailactiviteiten en geblokkeerde gebruikers via [waarschuwingsbeleid.](../../compliance/alert-policies.md)

EOP gebruikt uitgaand spambeleid als onderdeel van de algehele verdediging van uw organisatie tegen spam. Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.

Beheerders kunnen het standaard uitgaande spambeleid bekijken, bewerken en configureren (maar niet verwijderen). Voor een grotere granulariteit u ook aangepaste uitgaande spambeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U uitgaande spambeleidsregels configureren in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-klanten; Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a>Uitgaand spambeleid in het Security & Compliance Center vs Exchange Online PowerShell of Exchange Online Protection PowerShell

De basiselementen van een uitgaand spambeleid in EOP zijn:

- **Het uitgaande spamfilterbeleid**: hiermee geeft u de acties op voor uitgaande spamfilteruitspraken en de meldingsopties.

- **De regel voor uitgaand spamfilter**: hiermee geeft u de prioriteits- en ontvangerfilters op (op wie het beleid van toepassing is) voor een uitgaand spamfilterbeleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spam-polities beheert in het Security & Compliance Center:

- Wanneer u een uitgaand spambeleid maakt in het Security & Compliance Center, maakt u eigenlijk een uitgaande spamfilterregel en het bijbehorende uitgaande spamfilterbeleid tegelijkertijd met dezelfde naam voor beide.

- Wanneer u een uitgaand spambeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en de filters voor ontvangers de regel voor uitgaand spamfilter. Alle andere instellingen wijzigen het bijbehorende uitgaande spamfilterbeleid.

- Wanneer u een uitgaand spambeleid verwijdert uit het Security & Compliance Center, worden de regel voor uitgaand spamfilter en het bijbehorende uitgaande spamfilterbeleid verwijderd.

In Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell is het verschil zichtbaar tussen uitgaand spamfilterbeleid en uitgaande spamfilterregels. U beheert het beleid voor uitgaande spamfilters met behulp van de ** \*cmdlets -HostedOutboundSpamFilterPolicy** en u beheert uitgaande spamfilterregels met behulp van de ** \*cmdlets -HostedOutboundSpamFilterRule.**

- In PowerShell maakt u eerst het uitgaande spamfilterbeleid en vervolgens maakt u de regel voor uitgaande spamfilters die het beleid identificeert waarop de regel van toepassing is.

- In PowerShell wijzigt u de instellingen in het uitgaande spamfilterbeleid en de regel voor uitgaand spamfilter afzonderlijk.

- Wanneer u een uitgaand spamfilterbeleid uit PowerShell verwijdert, wordt de bijbehorende regel voor uitgaande spamfilters niet automatisch verwijderd en vice versa.

### <a name="default-outbound-spam-policy"></a>Standaard uitgaand spambeleid

Elke organisatie heeft een ingebouwd uitgaand spambeleid met de naam Default dat de volgende eigenschappen heeft:

- Het uitgaande spamfilterbeleid met de naam Standaard wordt toegepast op alle ontvangers in de organisatie, ook al is er geen uitgaande spamfilterregel (ontvangersfilters) gekoppeld aan het beleid.

- Het beleid met de naam Standaard heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.

- Het beleid met de naam Standaard is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Om de effectiviteit van uitgaande spamfilters te vergroten, u aangepaste uitgaande spambeleidsregels maken met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone Exchange Online Protection PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u uitgaande spambeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Voor alleen-lezen toegang tot uitgaande spambeleid moet u lid zijn van de rolgroep **Security Reader.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Zie [EOP-instellingen](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)voor uitgaande spambeleid voor onze aanbevolen instellingen voor uitgaande spam.

- Het [standaardwaarschuwingsbeleid](../../compliance/alert-policies.md) met de naam **E-mailverzendlimiet overschreden**, **Verdachte e-mailverzendpatronen gedetecteerd**en **gebruiker beperkt van het verzenden van e-mail** berichten al e-mail meldingen te sturen naar leden van de **TenantAdmins** (**Global admins**) groep over ongebruikelijke uitgaande e-mail activiteit en geblokkeerde gebruikers als gevolg van uitgaande spam. Zie [De waarschuwingsinstellingen voor gebruikers met beperkte toegang verifiëren voor](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)meer informatie. We raden u aan dit waarschuwingsbeleid te gebruiken in plaats van de meldingsopties in uitgaand spambeleid.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Gebruik het Security & Compliance Center om uitgaand spambeleid te maken

Als u een aangepast uitgaand spambeleid maakt in het Security & Compliance Center, wordt de spamfilterregel en het bijbehorende spamfilterbeleid tegelijkertijd met dezelfde naam voor beide gemaakt.

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispaminstellingen** op **Een uitgaand beleid maken**.

3. Configureer de volgende instellingen in het **beleid voor uitgaand spamfilter** dat wordt geopend:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

4. (Optioneel) Vouw de sectie **Meldingen** uit om extra gebruikers te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:

   - **Stuur een kopie van verdachte uitgaande e-mailberichten naar specifieke personen:** deze instelling voegt de opgegeven gebruikers als BCC-ontvangers toe aan de verdachte uitgaande berichten. Ga als volgt te werk om deze instelling in te schakelen:

     a. Schakel het selectievakje in om de instelling in te schakelen.

     b. Klik **op Personen toevoegen**. Ga als bedoeld als een flyout **voor geadresseerden toevoegen of verwijderen:**

     c. Voert u het e-mailadres van de afzender in. U meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één ontvanger per regel.

     d. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de ontvangers toe te voegen.

        Herhaal deze stappen zo vaak als nodig is.

        De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Adressenlijst** op de flyout. Als u een ![geadresseerde](../../media/scc-remove-icon.png)wilt verwijderen, klikt u op Knop Verwijderen .

     e. Klik op **Opslaan** wanneer u gereed bent.

     Schakel het selectievakje uit om deze instelling uit te schakelen.

   - **Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam:**

     > [!NOTE]
     > Het [standaardwaarschuwingsbeleid](../../compliance/alert-policies.md) met de naam **Gebruiker met de naam Gebruiker die geen e-mail** verzendt, stuurt al e-mailmeldingen naar leden van de groep **TenantAdministrators** **(Globale beheerders)** wanneer gebruikers worden geblokkeerd vanwege het overschrijden van de limieten in de sectie **Adressenlimieten.** We raden u aan het waarschuwingsbeleid te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers hiervan op de hoogte te stellen. Zie De [waarschuwingsinstellingen voor gebruikers met beperkte toegang controleren voor](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)instructies.

     Ga als volgt te werk om deze instelling in te schakelen:

     a. Schakel het selectievakje in om de instelling in te schakelen.

     b. Klik **op Personen toevoegen**. Ga als bedoeld als een flyout **voor geadresseerden toevoegen of verwijderen:**

     c. Voert u het e-mailadres van de afzender in. U meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één ontvanger per regel.

     d. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de ontvangers toe te voegen.

        Herhaal deze stappen zo vaak als nodig is.

        De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Adressenlijst** op de flyout. Als u een ![geadresseerde](../../media/scc-remove-icon.png)wilt verwijderen, klikt u op Knop Verwijderen .

     e. Klik op **Opslaan** wanneer u gereed bent.

     Schakel het selectievakje uit om deze instelling uit te schakelen.

5. (Optioneel) Vouw de sectie **Adressenlimieten** uit om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren:

   > [!NOTE]
   > Deze instellingen zijn alleen van toepassing op postvakken in de cloud.
     
   - **Maximum aantal ontvangers per gebruiker**

     Een geldige waarde is 0 tot 10000. De standaardwaarde is 0, wat betekent dat de standaardinstellingen van de service worden gebruikt. Zie [Limieten verzenden voor microsoft 365-opties voor](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)meer informatie.

     - **Externe uurlimiet**: Het maximum aantal externe ontvangers per uur.

     - **Interne uurlimiet**: Het maximum aantal interne ontvangers per uur.

     - **Dagelijkse limiet**: Het maximum aantal ontvangers per dag.

   - **Actie wanneer een gebruiker de bovenstaande limieten overschrijdt:** configureer de actie die moet worden uitgevoerd wanneer een van de limieten voor **geadresseerden** wordt overschreden. Voor alle acties ontvangen de ontvangers die in de gebruiker zijn opgegeven **het verzenden van e-mailwaarschuwingsbeleid** (en in het nu overbodige **Melden specifieke personen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spaminstellingen** in het uitgaande spambeleid, ontvangt u e-mailmeldingen.

     - **De gebruiker beperken van het verzenden van e-mail tot de volgende dag:** Dit is de standaardwaarde. E-mailmeldingen worden verzonden en de gebruiker kan tot de volgende dag geen berichten meer verzenden, op basis van utc-tijd. Er is geen manier voor de beheerder om dit blok te overschrijven.

       - De activiteitswaarschuwing met de naam **Gebruiker die geen e-mail verzendt,** waarschuwt beheerders (via e-mail en op de pagina **Waarschuwingen weergeven).**

       - Alle ontvangers die zijn opgegeven in de **melding van specifieke personen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spaminstellingen** in het beleid, worden ook op de hoogte gebracht.

       - De gebruiker kan tot de volgende dag geen berichten meer verzenden op basis van utc-tijd. Er is geen manier voor de beheerder om dit blok te overschrijven.

     - **Beperk de gebruiker van het verzenden van e-mail:** E-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan de portal **[Beperkte gebruikers]<https://sip.protection.office.com/restrictedusers> ** in het Security & Compliance Center en de gebruiker kan geen e-mail verzenden totdat ze door een beheerder van de portal **Voor beperkte gebruikers** zijn verwijderd. Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker die dag niet meer beperkt. Zie Een [gebruiker verwijderen uit de portal voor beperkte gebruikers verwijderen na het verzenden van spam-e-mail](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.

     - **Geen actie, alleen alert:** E-mailmeldingen worden verzonden.

6. (Vereist) Vouw de sectie **Toegepast op uit** om de interne afzenders te identificeren waarop het beleid van toepassing is.

    U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden met dezelfde voorwaarde of uitzondering gebruiken OR-logica (bijvoorbeeld _ \<afzender1\> _ of _ \<afzender2\>_). Verschillende voorwaarden of uitzonderingen gebruiken AND-logica (bijvoorbeeld _ \<afzender1\> _ en _ \<lid van groep 1\>_).

    Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven. U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.

    - **Het afzenderdomein is**: Hiermee geeft u afzenders op in een of meer van de geconfigureerde geaccepteerde domeinen in Office 365. Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren. Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.

    - **Afzender is:** Hiermee geeft u een of meer gebruikers in uw organisatie op. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik nogmaals op het vak **Een tag toevoegen** om extra afzenders te selecteren.

    - **Afzender is lid van**: Geeft een of meer groepen in uw organisatie op. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik nogmaals op het vak **Een tag toevoegen** om extra afzenders te selecteren.

    - **Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

7. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Het Beveiligings- & Compliance Center gebruiken om uitgaand spambeleid weer te geven

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispam-instellingen** op ![Pictogram](../../media/scc-expand-icon.png) Uitvouwen om een uitgaand spambeleid uit te vouwen:

   - Het standaardbeleid met de naam **Uitgaand spamfilterbeleid**.

   - Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** **aangepast uitgaand spambeleid**is.

3. De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven of u op **Beleid bewerken**klikken.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Het Beveiligingscentrum & Compliance Center gebruiken om uitgaand spambeleid te wijzigen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispam-instellingen** op ![Pictogram](../../media/scc-expand-icon.png) Uitvouwen om een uitgaand spambeleid uit te vouwen:

   - Het standaardbeleid met de naam **Uitgaand spamfilterbeleid**.

   - Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** **aangepast uitgaand spambeleid**is.

3. Klik op **Beleid bewerken**.

Voor aangepaste uitgaande spambeleidsregels zijn de beschikbare instellingen in de flyout die wordt weergegeven identiek aan die welke zijn beschreven in het beveiligings& Compliance Center gebruiken om een gedeelte [over uitgaand spambeleid te maken.](#use-the-security--compliance-center-to-create-outbound-spam-policies)

Voor het standaard uitgaande spambeleid met de naam **Uitgaand spamfilterbeleid**is de sectie **Toegepast op** niet beschikbaar (het beleid is voor iedereen van toepassing) en u de naam van het beleid niet wijzigen.

Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.

### <a name="enable-or-disable-outbound-spam-policies"></a>Uitgaand spambeleid in- of uitschakelen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispam-instellingen** op ![Pictogram Uitvouwen](../../media/scc-expand-icon.png) om een aangepast beleid uit te vouwen dat u hebt gemaakt (de waarde in de kolom **Type** is Aangepast **uitgaand spambeleid).**

3. Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.

   Verplaats te wisselknop naar links om het beleid uit te schakelen: ![Uitschakelen](../../media/scc-toggle-off.png)

   Verplaats te wisselknop naar rechts om het beleid in te schakelen: ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

U het standaard uitgaande spambeleid niet uitschakelen.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>De prioriteit instellen van aangepast uitgaand spambeleid

Uitgaand spambeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere politie's hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.

Aangepaste uitgaande spambeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0). Het standaard uitgaande spambeleid met de naam **Uitgaand spamfilterbeleid** heeft de prioriteitswaarde **Laagste**en u deze niet wijzigen.

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit**snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Zoek op de pagina **Antispam-instellingen** het beleid waarbij de waarde in de kolom **Type** **Aangepast uitgaand spambeleid**is. Let op de waarden in de kolom **Prioriteit**:

   - Het aangepaste uitgaande spambeleid met de ![hoogste prioriteit](../../media/ITPro-EAC-DownArrowIcon.png) heeft het waarde pijl-omlaag-pictogram **0**.

   - Het aangepaste uitgaande spambeleid met de ![laagste prioriteit](../../media/ITPro-EAC-UpArrowIcon.png) heeft de ![waarde Omhoog](../../media/ITPro-EAC-UpArrowIcon.png) pijl-pictogram **n** (bijvoorbeeld pijl-omhoog-pictogram **3**).

   - Als u drie of meer aangepaste uitgaande spambeleidsregels hebt, heeft ![het](../../media/ITPro-EAC-UpArrowIcon.png)![beleid tussen](../../media/ITPro-EAC-DownArrowIcon.png) de hoogste ![en laagste](../../media/ITPro-EAC-UpArrowIcon.png)![prioriteit](../../media/ITPro-EAC-DownArrowIcon.png) waarden Pictogram Pijl-omlaag **n** (bijvoorbeeld pictogram Pijl-omlaag **2**).

3. Klik op ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) of ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) om het aangepaste uitgaande spambeleid omhoog of omlaag te verplaatsen in de prioriteitenlijst.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Het Beveiligings- & Compliance Center gebruiken om uitgaand spambeleid te verwijderen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispam-instellingen** op ![Pictogram Uitvouwen](../../media/scc-expand-icon.png) om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom **Type** is Aangepast **uitgaand spambeleid).**

3. Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.

4. Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a>Exchange Online PowerShell of Exchange Online Protection PowerShell gebruiken om uitgaand spambeleid te configureren

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell gebruiken om uitgaand spambeleid te maken

Het maken van een uitgaand spambeleid in PowerShell is een proces in twee stappen:

1. Maak het beleid voor uitgaande spamfilters.

2. Maak de regel voor uitgaand spamfilter die het uitgaande spamfilterbeleid opgeeft waarop de regel van toepassing is.

 **Opmerkingen**:

- U een nieuwe regel voor uitgaande spamfilters maken en er een bestaand, niet-gekoppeld uitgaand spamfilterbeleid aan toewijzen. Een regel voor uitgaande spamfilters kan niet worden gekoppeld aan meer dan één uitgaand spamfilterbeleid.

- U de volgende instellingen configureren voor nieuwe uitgaande spamfilterbeleidsregels in PowerShell die pas beschikbaar zijn in het Beveiligings& Compliance Center nadat u het beleid hebt gemaakt:

  - Het nieuwe beleid als uitgeschakeld maken _(ingeschakeld_ `$false` op de cmdlet **Nieuw-HostedOutboundSpamFilterRule).**

  - Stel de prioriteit in van het beleid tijdens het maken ( _ \<Prioriteitsnummer\>_) op de cmdlet **Nieuw-HostedOutboundSpamFilterRule).** _Priority_

- Een nieuw uitgaand spamfilterbeleid dat u in PowerShell maakt, is pas zichtbaar in het Beveiligings- & Compliance Center als u het beleid aan een spamfilterregel toewijst.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Stap 1: PowerShell gebruiken om een uitgaand spamfilterbeleid te maken

Als u een uitgaand spamfilterbeleid wilt maken, gebruikt u de als volgt:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In dit voorbeeld wordt een nieuw uitgaand spamfilterbeleid gemaakt met de naam Contoso Executives met de volgende instellingen:

- De limieten voor het aantal ontvangers zijn beperkt tot kleinere waarden die in de standaardwaarden worden weergegeven. Zie [Limieten verzenden voor microsoft 365-opties voor](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)meer informatie.

- Nadat een van de limieten is bereikt, kan de gebruiker geen berichten meer verzenden.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Zie [Nieuw gehostOutboundSpamFilterBeleid](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Stap 2: PowerShell gebruiken om een uitgaande spamfilterregel te maken

Als u een regel voor uitgaand spamfilter wilt maken, gebruikt u de als volgt:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een nieuwe uitgaande spamfilterregel gemaakt met de naam Contoso Executives met de volgende instellingen:

- Het uitgaande spamfilterbeleid met de naam Contoso Executives is gekoppeld aan de regel.

- De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Zie [Nieuw gehostESpamFilterRegel](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell gebruiken om uitgaand spamfilterbeleid weer te geven

Voer de opdracht uit om een overzichtslijst met alle uitgaande spamfilterbeleidsregels terug te geven:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Als u gedetailleerde informatie over een specifiek uitgaand spamfilterbeleid wilt retourneren, gebruikt u de als volgt:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In dit voorbeeld worden alle eigenschapswaarden voor het uitgaande spamfilterbeleid met de naam Executives geretourneerd.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell gebruiken om uitgaande spamfilterregels weer te geven

Als u bestaande regels voor uitgaande spamfilters wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Voer de opdracht uit om een overzichtslijst met alle uitgaande spamfilterregels terug te sturen:

```PowerShell
Get-HostedOutboundSpamFilterRule
```

Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

Als u gedetailleerde informatie over een specifieke regel voor uitgaand spamfilter wilt retourneren, gebruikt u de als volgt:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In dit voorbeeld worden alle eigenschapswaarden voor de uitgaande spamfilterregel met de naam Contoso Executives geretourneerd.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell gebruiken om uitgaand spamfilterbeleid te wijzigen

Dezelfde instellingen zijn beschikbaar wanneer u een beleid voor malwarefilters in PowerShell wijzigt, zoals wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit onderwerp een gedeelte [over uitgaand beleid voor spamfilters te maken.](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy)

**Opmerking:** U de naam van een uitgaand spamfilterbeleid niet wijzigen (de cmdlet **Set-HostedOutboundSpamFilterPolicy** heeft geen _parameter Name)._ Wanneer u de naam van een uitgaand spambeleid wijzigt in het Security & Compliance Center, wijzigt u alleen de naam van de regel voor uitgaande _spamfilters._

Als u een uitgaand spamfilterbeleid wilt wijzigen, gebruikt u de als volgt:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-HostedOutboundSpamFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters te wijzigen

De enige instelling die niet beschikbaar is wanneer u een uitgaande spamfilterregel in PowerShell wijzigt, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken. Zie de volgende sectie om bestaande regels voor uitgaande spamfilters in te schakelen of uit te schakelen.

Anders zijn er geen aanvullende instellingen beschikbaar wanneer u een uitgaande spamfilterregel in PowerShell wijzigt. Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een regelsectie voor uitgaande spamfilters te maken.](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)

Als u een regel voor uitgaand spamfilter wilt wijzigen, gebruikt u de als volgt:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Zie [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters in te schakelen of uit te schakelen

Als u een uitgaande spamfilterregel in PowerShell in- of uitschakelt, schakelt u het hele uitgaande spambeleid in of uit (de regel voor uitgaand spamfilter en het toegewezen uitgaande spamfilterbeleid). U het standaard uitgaande spambeleid niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).

Gebruik de als volgt te houden om een regel voor uitgaand spamfilter in PowerShell in te schakelen of uit te schakelen:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de regel voor het uitgaande spamfilter met de naam Marketing Department uitgeschakeld.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [IngebouwdeSpamFilterRegel inschakelenEnen](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) [UitschakelenOutboundOfEnRegel en HostedOutboundSpamFilterRule uitschakelen voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell gebruiken om de prioriteit van uitgaande spamfilterregels in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit van een uitgaande spamfilterregel in PowerShell wilt instellen, gebruikt u de volgende syntaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**Opmerkingen**:

- Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Priority_ op de cmdlet **Nieuw-HostedOutboundSpamFilterRule.**

- Het uitgaande standaardspamfilterbeleid heeft geen bijbehorende spamfilterregel en heeft altijd de onaanpasbare prioriteitswaarde **Laagste**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell gebruiken om uitgaand spamfilterbeleid te verwijderen

Wanneer u PowerShell gebruikt om een uitgaand spamfilterbeleid te verwijderen, wordt de bijbehorende regel voor uitgaand spamfilter niet verwijderd.

Als u een uitgaand spamfilterbeleid in PowerShell wilt verwijderen, gebruikt u de als volgt:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het uitgaande spamfilterbeleid met de naam MarketingAfdeling verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Zie [Beleid verwijderen-gehostOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters te verwijderen

Wanneer u PowerShell gebruikt om een uitgaande spamfilterregel te verwijderen, wordt het bijbehorende uitgaande spamfilterbeleid niet verwijderd.

Als u een regel voor uitgaand spamfilter in PowerShell wilt verwijderen, gebruikt u de als volgt:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de regel voor het uitgaande spamfilter met de naam Marketing Department verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="for-more-information"></a>Voor meer informatie

[Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten](removing-user-from-restricted-users-portal-after-spam.md)

[Groep met verhoogd risico voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md)

[Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.md)
