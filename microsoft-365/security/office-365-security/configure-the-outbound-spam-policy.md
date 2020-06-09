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
description: Beheerders kunnen in Exchange Online Protection (EOP) leren hoe ze uitgaand spambeleid kunnen bekijken, maken, wijzigen en verwijderen.
ms.openlocfilehash: 6a15e33033643f99fc8aeb51036ddac7beba7b71
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616576"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Uitgaande spamfiltering configureren in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken worden uitgaande e-mailberichten die via EOP worden verzonden, automatisch gecontroleerd op spam en ongebruikelijke verzendende activiteiten.

Uitgaande spam van een gebruiker in uw organisatie duidt meestal op een gecompromitteerd account. Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het spamvertrouwensniveau of SCL) en worden doorgestuurd via de [leveringspool met een hoog risico](high-risk-delivery-pool-for-outbound-messages.md) om de reputatie van de service te beschermen (dat wil zeggen, houd Microsoft 365-brone-mailservers buiten IP-bloklijsten). Beheerders worden automatisch op de hoogte gesteld van verdachte uitgaande e-mailactiviteiten en geblokkeerde gebruikers via [waarschuwingsbeleid.](../../compliance/alert-policies.md)

EOP gebruikt uitgaand spambeleid als onderdeel van de algehele verdediging van uw organisatie tegen spam. Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.

Beheerders kunnen het standaard outbound spambeleid bekijken, bewerken en configureren (maar niet verwijderen). Voor meer granulariteit u ook aangepaste uitgaande spambeleid maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U uitgaand spambeleid configureren in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a>Uitgaand spambeleid in het Security & Compliance Center vs PowerShell

De basiselementen van een uitgaand spambeleid in EOP zijn:

- **Het beleid voor uitgaande spamfilter:** geeft de acties op voor uitgaande spamfiltervonnten en de meldingsopties.

- **De regel van het uitgaande spamfilter:** hiermee geeft u de prioriteits- en ontvangerfilters op (op wie het beleid van toepassing is) voor een outbound spamfilterbeleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spampolitie beheert in het Security & Compliance Center:

- Wanneer u een uitgaand spambeleid maakt in het Security & Compliance Center, maakt u een uitgaande spamfilterregel en het bijbehorende beleid voor uitgaande spamfilter tegelijkertijd met dezelfde naam voor beide.

- Wanneer u een uitgaand spambeleid wijzigt in het Security & Compliance Center, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld, en ontvangersfilters de regel van het uitgaande spamfilter. Alle andere instellingen wijzigen het bijbehorende outbound spamfilterbeleid.

- Wanneer u een uitgaand spambeleid verwijdert uit het Security & Compliance Center, worden de regel voor uitgaande spamfilter en het bijbehorende beleid voor uitgaande spamfilters verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell is het verschil tussen het beleid voor uitgaande spamfilters en uitgaande regels voor spamfilters zichtbaar. U beheert uitgaande spamfilterbeleid met behulp van de cmdlets ** \* HostedOutboundSpamFilterPolicy** en beheert uitgaande regels voor spamfilters met behulp van de cmdlets ** \* HostedOutboundSpamFilter.**

- In PowerShell maakt u eerst het beleid voor uitgaande spamfilters en vervolgens maakt u de regel voor uitgaande spamfilters die het beleid identificeert waarop de regel van toepassing is.

- In PowerShell wijzigt u de instellingen in het beleid voor uitgaande spamfilters en de regel van het uitgaande spamfilter afzonderlijk.

- Wanneer u een uitgaand spamfilterbeleid uit PowerShell verwijdert, wordt de bijbehorende regel voor uitgaande spamfilter niet automatisch verwijderd en vice versa.

### <a name="default-outbound-spam-policy"></a>Standaard outbound spambeleid

Elke organisatie heeft een ingebouwd outbound spambeleid met de naam Standaard met de volgende eigenschappen:

- Het uitgaande spamfilterbeleid met de naam Standaard wordt toegepast op alle ontvangers in de organisatie, ook al is er geen uitgaande spamfilterregel (geadresseerdefilters) die aan het beleid is gekoppeld.

- Het beleid met de naam Standaard heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.

- Het beleid met de naam Standaard is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Om de effectiviteit van uitgaande spamfiltering te vergroten, u aangepaste uitgaande spambeleid maken met strengere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u uitgaand spambeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.** Voor alleen-lezen toegang tot uitgaand spambeleid moet u lid zijn van de rolgroep **Beveiligingslezer.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Zie Beleidsinstellingen voor [EOP-uitgaande spamfilters](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)voor onze aanbevolen instellingen voor uitgaande spambeleid.

- Het [standaardwaarschuwingsbeleid](../../compliance/alert-policies.md) met de naam **E-mail verzenden overschreden,** **Verdachte e-mailverzendpatronen gedetecteerd**en **Gebruiker beperkt van het verzenden van e-mail** al e-mail meldingen sturen naar leden van de **TenantAdmins** **(Global admins)** groep over ongebruikelijke uitgaande e-mail activiteit en geblokkeerde gebruikers als gevolg van uitgaande spam. Zie [De waarschuwingsinstellingen voor beperkte gebruikers verifiëren](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)voor meer informatie. We raden u aan dit waarschuwingsbeleid te gebruiken in plaats van de meldingsopties in het uitgaande spambeleid.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Gebruik het Security & Compliance Center om uitgaand spambeleid te maken

Als u een aangepast outbound spambeleid maakt in het Security & Compliance Center, worden tegelijkertijd de regel voor spamfilter en het bijbehorende spamfilterbeleid met dezelfde naam voor beide gemaakt.

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispam-instellingen** op **Een uitgaand beleid maken**.

3. Configureer in het **beleid voor uitgaande spamfilters** dat wordt geopend de volgende instellingen:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

4. (Optioneel) Vouw de sectie **Meldingen** uit om extra gebruikers te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:

   - **Een kopie van verdachte uitgaande e-mailberichten verzenden naar specifieke personen:** met deze instelling worden de opgegeven gebruikers als BCC-ontvangers toegevoegd aan de verdachte uitgaande berichten.

     > [!NOTE]
     > Deze instelling werkt alleen in het standaard uitgaande spambeleid. Het werkt niet in het aangepaste uitgaande spambeleid dat u maakt.

     Ga als volgt te werk om deze instelling in te schakelen:

     a. Schakel het selectievakje in om de instelling in te schakelen.

     b. Klik **op Personen toevoegen**. In de flyout **voor geadresseerden toevoegen of verwijderen** die wordt weergegeven:

     c. Voert u het e-mailadres van de afzender in. U meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één ontvanger per regel.

     d. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de ontvangers toe te voegen.

        Herhaal deze stappen zo vaak als nodig is.

        De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Geadresseerdelijst** in de flyout. Als u een ontvanger wilt verwijderen, klikt u op ![ knop Verwijderen ](../../media/scc-remove-icon.png) .

     e. Klik op **Opslaan** wanneer u gereed bent.

     Schakel het selectievakje uit om deze instelling uit te schakelen.

   - **Informeer specifieke personen als een afzender is geblokkeerd als gevolg van het verzenden van uitgaande spam:**

     > [!NOTE]
     > Het [standaardwaarschuwingsbeleid](../../compliance/alert-policies.md) met de naam **Gebruiker die is beperkt tot het verzenden van e-mail,** stuurt al e-mailmeldingen naar leden van de groep **TenantAdmins** **(Globale beheerders)** wanneer gebruikers worden geblokkeerd vanwege het overschrijden van de limieten in de sectie **Geadresseerdelimieten.** We raden u aan het waarschuwingsbeleid te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers op de hoogte te stellen. Zie De [waarschuwingsinstellingen voor beperkte gebruikers verifiëren](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)voor instructies. <br/><br/> Deze instelling werkt alleen in het standaard uitgaande spambeleid. Het werkt niet in het aangepaste uitgaande spambeleid dat u maakt.

     Ga als volgt te werk om deze instelling in te schakelen:

     a. Schakel het selectievakje in om de instelling in te schakelen.

     b. Klik **op Personen toevoegen**. In de flyout **voor geadresseerden toevoegen of verwijderen** die wordt weergegeven:

     c. Voert u het e-mailadres van de afzender in. U meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één ontvanger per regel.

     d. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de ontvangers toe te voegen.

        Herhaal deze stappen zo vaak als nodig is.

        De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Geadresseerdelijst** in de flyout. Als u een ontvanger wilt verwijderen, klikt u op ![ knop Verwijderen ](../../media/scc-remove-icon.png) .

     e. Klik op **Opslaan** wanneer u gereed bent.

     Schakel het selectievakje uit om deze instelling uit te schakelen.

5. (Optioneel) Vouw de sectie **Geadresseerdelimieten** uit om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren:

   > [!NOTE]
   > Deze instellingen zijn alleen van toepassing op postvakken in de cloud.

   - **Maximaal aantal ontvangers per gebruiker**

     Een geldige waarde is 0 tot 10000. De standaardwaarde is 0, wat betekent dat de standaardinstellingen voor de service worden gebruikt. Zie [Limieten verzenden voor Microsoft 365-opties](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)voor meer informatie.

     - **Externe uurlimiet**: Het maximum aantal externe ontvangers per uur.

     - **Interne uurlimiet**: Het maximum aantal interne ontvangers per uur.

     - **Daglimiet**: Het maximale totale aantal ontvangers per dag.

   - **Actie wanneer een gebruiker de bovenstaande limieten overschrijdt:** Configureer de actie die u moet uitvoeren wanneer een van de **geadresseerdelimieten** wordt overschreden. Voor alle acties mogen de ontvangers die zijn opgegeven in de **gebruiker geen e-mailwaarschuwingsbeleid verzenden** (en in het nu redundante Specifieke personen melden als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spamin** het uitgaande spambeleid, e-mailmeldingen ontvangen.

     - **Beperk de gebruiker van het verzenden van e-mail tot de volgende dag:** Dit is de standaardwaarde. E-mailmeldingen worden verzonden en de gebruiker kan tot de volgende dag geen berichten meer verzenden op basis van UTC-tijd. Er is geen manier voor de beheerder om dit blok te overschrijven.

       - De activiteitswaarschuwing met de naam **Gebruiker die geen e-mail mag verzenden,** waarschuwt beheerders (via e-mail en op de pagina **Waarschuwingen weergeven).**

       - Alle ontvangers die zijn opgegeven in de **specifieke personen melden als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam-instelling** in het beleid, worden ook op de hoogte gesteld.

       - De gebruiker kan tot de volgende dag geen berichten meer verzenden op basis van UTC-tijd. Er is geen manier voor de beheerder om dit blok te overschrijven.

     - **Beperk de gebruiker van het verzenden van e-mail:** e-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan de portal **[Beperkte gebruikers] <https://sip.protection.office.com/restrictedusers> ** in het Security & Compliance Center en de gebruiker kan geen e-mail verzenden totdat deze door een beheerder uit de portal **Beperkte gebruikers** is verwijderd. Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker niet opnieuw beperkt voor die dag. Zie Een [gebruiker verwijderen uit de portal Beperkte gebruikers na het verzenden van spam-e-mail](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.

     - **Geen actie, alleen alert**: E-mailmeldingen worden verzonden.

6. (vereist) Vouw de sectie **Toegepast op** uit om de interne afzenders te identificeren waarop het beleid van toepassing is.

    U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden met dezelfde voorwaarde of uitzondering gebruiken OR-logica _\<sender1\>_ (bijvoorbeeld, of _\<sender2\>_ ). Verschillende voorwaarden of uitzonderingen gebruiken EN-logica (bijvoorbeeld _\<sender1\>_ en _\<member of group 1\>_ ).

    Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven. U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.

    - **Het afzenderdomein is:** Hiermee geeft u afzenders op in een of meer van de geconfigureerde geaccepteerde domeinen in de organisatie. Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren. Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.

    - **Afzender is:** Hiermee geeft u een of meer gebruikers in uw organisatie op. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik nogmaals op het vak **Een tag toevoegen** om extra afzenders te selecteren.

    - **Afzender is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik nogmaals op het vak **Een tag toevoegen** om extra afzenders te selecteren.

    - **Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

7. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Gebruik het Security & Compliance Center om uitgaand spambeleid te bekijken

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispaminstellingen** op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:

   - Het standaardbeleid met de naam **Uitgaande spamfilterbeleid**.

   - Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** **aangepast uitgaande spambeleid**is.

3. De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven of u op **Beleid bewerken**klikken.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Gebruik het Security & Compliance Center om uitgaand spambeleid te wijzigen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispaminstellingen** op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:

   - Het standaardbeleid met de naam **Uitgaande spamfilterbeleid**.

   - Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** **aangepast uitgaande spambeleid**is.

3. Klik op **Beleid bewerken**.

Voor aangepaste uitgaande spambeleid zijn de beschikbare instellingen in de flyout die wordt weergegeven identiek aan die beschreven in de sectie [Beveiligingscentrum & Compliance om uitgaande spambeleid te maken.](#use-the-security--compliance-center-to-create-outbound-spam-policies)

Voor het standaardbeleid voor uitgaande spam met de naam **Uitgaande spamfilterbeleid**is de sectie **Toegepast op** niet beschikbaar (het beleid is voor iedereen van toepassing) en u de naam van het beleid niet wijzigen.

Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.

### <a name="enable-or-disable-outbound-spam-policies"></a>Uitgaand spambeleid in- of uitschakelen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispaminstellingen** op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) om een aangepast beleid uit te vouwen dat u hebt gemaakt (de waarde in de kolom **Type** is **aangepast uitgaand spambeleid).**

3. Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.

   Verplaats te wisselknop naar links om het beleid uit te schakelen: ![Uitschakelen](../../media/scc-toggle-off.png)

   Verplaats te wisselknop naar rechts om het beleid in te schakelen: ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

U het standaardbeleid voor uitgaande spam niet uitschakelen.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>De prioriteit van het aangepaste uitgaande spambeleid instellen

Het uitgaande spambeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere polities hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee verschillende beleidsregels kunnen niet dezelfde prioriteit hebben.

Aangepaste uitgaande spambeleid wordt weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0). Het standaardvermelde spambeleid met de naam **Uitgaande spamfilterbeleid** heeft de **prioriteitswaarde Laagste**en u het niet wijzigen.

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit**snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Zoek op de pagina **Antispam-instellingen** het beleid waarbij de waarde in de kolom **Type** **aangepast uitgaande spambeleid**is. Let op de waarden in de kolom **Prioriteit**:

   - Het aangepaste uitgaande spambeleid met de hoogste prioriteit heeft het ![ pictogram Pijl-omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Het aangepaste uitgaande spambeleid met de laagste prioriteit heeft het ![ pictogram Pijl-omhoog ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (bijvoorbeeld ![ Omhoog Pijl-pictogram ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Als u drie of meer aangepaste uitgaande spambeleid hebt, bevat het beleid tussen de hoogste en de laagste prioriteit het ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ pictogram Pijl-omhoog-pijl-omhoogpictogram ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (bijvoorbeeld ![ pictogram Pijl-omhoog-pijl-omlaag ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Klik op ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) of ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) om het aangepaste uitgaande spambeleid omhoog of omlaag te verplaatsen in de prioriteitenlijst.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Gebruik het Security & Compliance Center om uitgaande spambeleid te verwijderen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispaminstellingen** op ![ Pictogram Uitvouwen ](../../media/scc-expand-icon.png) om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom **Type** is **aangepast uitgaand spambeleid).**

3. Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.

4. Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om uitgaand spambeleid te configureren

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell gebruiken om uitgaand spambeleid te maken

Het maken van een uitgaand spambeleid in PowerShell is een proces in twee stappen:

1. Maak het beleid voor uitgaande spamfilters.

2. Maak de regel voor uitgaande spamfilters die het uitgaande spamfilterbeleid opgeeft waarop de regel van toepassing is.

 **Opmerkingen**:

- U een nieuwe regel voor uitgaande spamfilters maken en er een bestaand, niet-gekoppeld outbound spamfilterbeleid aan toewijzen. Een uitgaande spamfilterregel kan niet worden gekoppeld aan meer dan één outbound spamfilterbeleid.

- U de volgende instellingen configureren voor nieuw beleid voor uitgaande spamfilters in PowerShell dat pas beschikbaar is in het Security & Compliance Center nadat u het beleid hebt gemaakt:

  - Maak het nieuwe beleid als uitgeschakeld (_Ingeschakeld_ `$false` op de cmdlet **New-HostedOutboundSpamFilterRule).**

  - Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ _\<Number\>_ op de cmdlet **New-HostedOutboundSpamFilterRule).**

- Een nieuw beleid voor uitgaande spamfilters dat u maakt in PowerShell, is pas zichtbaar in het Security & Compliance Center totdat u het beleid toewijst aan een spamfilterregel.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Stap 1: PowerShell gebruiken om een outbound spamfilterbeleid te maken

Als u een beleid voor uitgaande spamfilters wilt maken, gebruikt u deze syntaxis:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In dit voorbeeld wordt een nieuw beleid voor uitgaande spamfilters gemaakt met de naam Contoso Executives met de volgende instellingen:

- De tarieflimieten voor ontvangers zijn beperkt tot kleinere waarden die de standaardwaarden hebben. Zie [Limieten verzenden voor Microsoft 365-opties](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)voor meer informatie.

- Nadat een van de limieten is bereikt, kan de gebruiker geen berichten verzenden.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Zie [Nieuw-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis en parametergegevens .

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Stap 2: PowerShell gebruiken om een regel voor uitgaande spamfilters te maken

Als u een regel voor uitgaande spamfilter wilt maken, gebruikt u deze syntaxis:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een nieuwe regel voor uitgaande spamfilters gemaakt met de naam Contoso Executives met de volgende instellingen:

- Het uitgaande spamfilterbeleid met de naam Contoso Executives is gekoppeld aan de regel.

- De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Zie [Nieuw-HostedOutboundSpamFilterRule voor](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)gedetailleerde syntaxis en parametergegevens .

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell gebruiken om het beleid voor uitgaande spamfilters weer te geven

Voer deze opdracht uit om een overzichtslijst met alle uitgaande spamfilterregels terug te sturen:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Als u gedetailleerde informatie over een specifiek beleid voor uitgaande spamfilters wilt retourneren, gebruikt u de syntaxis:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor het beleid voor uitgaande spamfilter met de naam Leidinggevenden.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis en parametergegevens .

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell gebruiken om uitgaande regels voor spamfilters weer te geven

Als u bestaande regels voor uitgaande spamfilters wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Voer deze opdracht uit om een overzichtslijst met alle regels voor uitgaande spamfilters terug te sturen:

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

Als u gedetailleerde informatie over een specifieke regel voor uitgaande spamfilter wilt retourneren, gebruikt u deze syntaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In dit voorbeeld worden alle eigenschapswaarden geretourneerd voor de regel voor het uitgaande spamfilter met de naam Contoso Executives.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis en parametergegevens .

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell gebruiken om het beleid voor uitgaande spamfilters te wijzigen

Dezelfde instellingen zijn beschikbaar wanneer u een beleid voor malwarefilters wijzigt in PowerShell als wanneer u het beleid maakt zoals beschreven in [stap 1: PowerShell gebruiken om](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) eerder in dit onderwerp een uitgaande sectie voor spamfilterbeleid te maken.

**Opmerking**: U de naam van een outbound spamfilterbeleid niet wijzigen (de cmdlet **Set-HostedOutboundSpamFilterPolicy** heeft geen parameter _Name)._ Wanneer u de naam van een uitgaande spambeleid wijzigt in het Security & Compliance Center, wijzigt u alleen de _regel_van het uitgaande spamfilter .

Als u een beleid voor uitgaande spamfilters wilt wijzigen, gebruikt u deze syntaxis:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-HostedOutboundSpamFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)gedetailleerde syntaxis en parametergegevens .

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell gebruiken om de regels voor uitgaande spamfilters te wijzigen

De enige instelling die niet beschikbaar is wanneer u een uitgaande spamfilterregel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel maken. Zie de volgende sectie om bestaande regels voor uitgaande spamfilters in of uit te schakelen.

Anders zijn er geen extra instellingen beschikbaar wanneer u een regel voor uitgaande spamfilters wijzigt in PowerShell. Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit onderwerp [een regelsectie voor uitgaande spamfilters te maken.](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule)

Als u een regel voor uitgaande spamfilters wilt wijzigen, gebruikt u deze syntaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Zie [Set-HostedOutboundSpamFilterRule voor](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)gedetailleerde syntaxis en parametergegevens .

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilter in of uit te schakelen

Als u een uitgaande spamfilterregel inschakelt of uitschakelt in PowerShell, wordt het hele uitgaande spambeleid (de regel van het uitgaande spamfilter en het toegewezen outbound spamfilterbeleid) in- of uitgeschakeld. U het standaard uitgaande spambeleid niet in- of uitschakelen (het wordt altijd toegepast op alle ontvangers).

Als u een regel voor uitgaande spamfilters in PowerShell wilt in- of uitschakelen, gebruikt u deze syntaxis:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de regel voor uitgaande spamfilter marketing uitgeschakeld.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) en [HostedOutboundSpamFilterRule uitschakelen](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis en parametergegevens .

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell gebruiken om de prioriteit van regels voor uitgaande spamfilters in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit van een regel voor uitgaande spamfilters wilt instellen in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**Opmerkingen**:

- Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New-HostedOutboundSpamFilterRule.**

- Het uitgaande standaardspamfilterbeleid heeft geen bijbehorende spamfilterregel en heeft altijd de onmodifiable **prioriteitswaarde Laagste**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell gebruiken om het beleid voor uitgaande spamfilters te verwijderen

Wanneer u PowerShell gebruikt om een outbound spamfilterbeleid te verwijderen, wordt de bijbehorende regel voor uitgaande spamfilters niet verwijderd.

Als u een beleid voor uitgaande spamfilters in PowerShell wilt verwijderen, gebruikt u deze syntaxis:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het beleid voor uitgaande spamfilter met de naam Marketing department verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Zie [Remove-HostedOutboundSpamFilterPolicy verwijderen](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis en parametergegevens .

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters te verwijderen

Wanneer u PowerShell gebruikt om een uitgaande spamfilterregel te verwijderen, wordt het bijbehorende beleid voor uitgaande spamfilters niet verwijderd.

Als u een regel voor uitgaande spamfilters in PowerShell wilt verwijderen, gebruikt u deze syntaxis:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de regel voor uitgaande spamfilter marketing verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [Remove-HostedOutboundSpamFilterRule verwijderen](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis en parametergegevens .

## <a name="for-more-information"></a>Voor meer informatie

[Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten](removing-user-from-restricted-users-portal-after-spam.md)

[Groep met verhoogd risico voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md)

[Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.md)
