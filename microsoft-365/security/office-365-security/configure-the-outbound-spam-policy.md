---
title: Filteren van uitgaande spam configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over het weergeven, maken, wijzigen en verwijderen van uitgaand spambeleid in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2448bb7942f7694d2a6d6e9b98537a2b7ccb14d1
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331668"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Uitgaande spamfilters configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online-postvakken, worden uitgaande e-mailberichten die via EOP worden verzonden, automatisch gecontroleerd op spam en ongebruikelijke verzendingsactiviteiten.

Uitgaande spam van een gebruiker in uw organisatie geeft meestal een gekromd account aan. Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het betrouwbaarheidsniveau voor spam of SCL) en worden door de groep met risicovolle bezorging gerouteerd om de reputatie van de service te beschermen (dat wil zeggen dat Microsoft 365 bron-e-mailservers buiten [ip-bloklijsten](high-risk-delivery-pool-for-outbound-messages.md) blijven). Beheerders worden automatisch op de hoogte gesteld van verdachte uitgaande e-mailactiviteit en geblokkeerde gebruikers via [waarschuwingsbeleid.](../../compliance/alert-policies.md)

EOP gebruikt uitgaand spambeleid als onderdeel van de algemene verdediging van uw organisatie tegen spam. Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.

Beheerders kunnen het standaardbeleid voor uitgaande spam weergeven, bewerken en configureren (maar niet verwijderen). Voor meer granulariteit kunt u ook aangepaste uitgaande spambeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U kunt uitgaand spambeleid configureren in het Beveiligings- & Compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

De basiselementen van een uitgaand spambeleid in EOP zijn:

- **Het beleid voor uitgaand spamfilter:** geeft de acties voor uitgaande spamfilters en de meldingsopties op.
- **De regel voor uitgaand spamfilter:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een uitgaand spamfilterbeleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spam polices beheert in het Beveiligings- & Compliance center:

- Wanneer u een beleid maakt, maakt u tegelijkertijd een regel voor uitgaand spamfilter en het bijbehorende beleid voor uitgaand spamfilter met dezelfde naam voor beide.
- Wanneer u een beleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en adressenfilters de regel voor uitgaand spamfilter. Alle andere instellingen wijzigen het bijbehorende beleid voor uitgaand spamfilter.
- Wanneer u een beleid verwijdert, worden de regel voor uitgaand spamfilter en het bijbehorende beleid voor uitgaand spamfilter verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Gebruik Exchange Online PowerShell of zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) voor het configureren van uitgaand spambeleid verderop in dit artikel voor meer informatie.

Elke organisatie heeft een ingebouwd uitgaand spambeleid met de naam Standaard met de volgende eigenschappen:

- Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen regel voor uitgaand spamfilter (geadresseerdenfilters) gekoppeld aan het beleid.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Als u de effectiviteit van uitgaande spamfilters wilt vergroten, kunt u aangepaste uitgaande spambeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u uitgaande spambeleidsregels wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Als u alleen-lezen toegang wilt tot uitgaand spambeleid, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie [EOP outbound spamfilterbeleidsinstellingen](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)voor onze aanbevolen instellingen voor uitgaand spambeleid.

- De [](../../compliance/alert-policies.md) standaardwaarschuwingsbeleidsregels met de naam Verzendlimiet voor e-mail zijn **overschreden,** Verdachte patronen voor het verzenden van e-mail zijn gedetecteerd en gebruikers kunnen geen e-mailmeldingen verzenden naar leden van de **groep TenantAdmins** **(Globale** beheerders) over ongebruikelijke uitgaande e-mailactiviteit en geblokkeerde gebruikers vanwege uitgaande spam.  Zie De waarschuwingsinstellingen voor beperkte gebruikers controleren [voor meer informatie.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) U wordt aangeraden dit waarschuwingsbeleid te gebruiken in plaats van de meldingsopties in uitgaand spambeleid.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Gebruik het Beveiligings- & compliancecentrum om uitgaand spambeleid te maken

Als u een aangepast uitgaand spambeleid maakt in het Beveiligings- & Compliancecentrum, worden de filterregel voor spam en het bijbehorende spamfilterbeleid tegelijkertijd gemaakt met dezelfde naam voor beide.

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispam-instellingen** op **Uitgaand beleid maken.**

3. Configureer de volgende instellingen in het beleid voor uitgaand **spamfilter** dat wordt geopend:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

4. (Optioneel) Vouw de **sectie Meldingen uit** om extra gebruikers te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:

   - **Een kopie van verdachte uitgaande** e-mailberichten naar specifieke personen verzenden: met deze instelling worden de opgegeven gebruikers als BCC-geadresseerden toegevoegd aan de verdachte uitgaande berichten.

     > [!NOTE]
     > Deze instelling werkt alleen in het standaardbeleid voor uitgaande spam. Het werkt niet in aangepaste uitgaande spambeleidsregels die u maakt.

     Als u deze instelling wilt inschakelen:

     1. Schakel het selectievakje in om de instelling in te stellen.

     1. Klik **op Personen toevoegen.** In het **flyout Geadresseerden toevoegen of** verwijderen dat wordt weergegeven:

     1. Voert u het e-mailadres van de afzender in. U kunt meerdere e-mailadressen opgeven die zijn gescheiden door puntkomma's (;) of één geadresseerde per regel.

     1. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de geadresseerden toe te voegen.

        Herhaal deze stappen zo vaak als nodig is.

        De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **Lijst met** geadresseerden in de flyout. Als u een geadresseerde wilt verwijderen, klikt ![ u op Knop ](../../media/scc-remove-icon.png) Verwijderen.

     1. Klik op **Opslaan** wanneer u gereed bent.

        Als u deze instelling wilt uitschakelen, schakelt u het selectievakje uit.

   - **Informeer specifieke personen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam:**

     > [!IMPORTANT]
     >
     > - Deze instelling wordt momenteel verwijderd uit uitgaand spambeleid.
     >
     > - Het [](../../compliance/alert-policies.md) standaardwaarschuwingsbeleid met de naam **Gebruiker** die geen e-mail mag verzenden, verzendt al e-mailmeldingen naar leden van de **groep TenantAdmins** **(Globale** beheerders) wanneer gebruikers worden geblokkeerd vanwege het overschrijden van de limieten in de sectie Geadresseerdenlimieten.  **We raden u ten zeerste aan het waarschuwingsbeleid** te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers op de hoogte te stellen. Zie De [waarschuwingsinstellingen voor](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)beperkte gebruikers controleren voor instructies.

5. (Optioneel) Vouw de **sectie Geadresseerdenlimieten** uit om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren:

   > [!NOTE]
   > Deze instellingen zijn alleen van toepassing op postvakken in de cloud.

   - **Maximum aantal geadresseerden per gebruiker**

     Een geldige waarde is 0 tot 10000. De standaardwaarde is 0, wat betekent dat de service-standaardwaarden worden gebruikt. Zie Limieten verzenden [voor meer informatie.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

     - **Externe uurlimiet:** het maximum aantal externe geadresseerden per uur.

     - **Interne uurlimiet:** het maximum aantal interne geadresseerden per uur.

     - **Daglimiet:** Het maximumtotaal aantal geadresseerden per dag.

   - **Actie wanneer een gebruiker de bovenstaande limieten** overschrijdt: Configureer de actie die moet worden ondernomen wanneer een van de limieten voor **geadresseerden** wordt overschreden. Voor alle acties hebben de geadresseerden die in de gebruiker zijn opgegeven, het verzenden van e-mailwaarschuwingsbeleid beperkt (en in het nu redundante Bericht specifieke personen informeren als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam in het uitgaande **spambeleid** ontvangen e-mailmeldingen. 

     - **De gebruiker beperken van het verzenden van e-mail tot de volgende dag:** dit is de standaardwaarde. Er worden e-mailmeldingen verzonden en de gebruiker kan geen berichten meer verzenden tot de volgende dag, op basis van UTC-tijd. De beheerder kan dit blok niet overschrijven.

       - De activiteitswaarschuwing **met de naam Gebruiker die geen e-mail** mag verzenden, meldt beheerders (via e-mail en op de pagina **Waarschuwingen** weergeven).

       - Geadresseerden die zijn opgegeven in de instelling Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spam** in het beleid, worden ook op de hoogte gesteld.

       - De gebruiker kan geen berichten meer verzenden tot de volgende dag, op basis van UTC-tijd. De beheerder kan dit blok niet overschrijven.

     - De gebruiker beperken van het verzenden van e-mail: e-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan de **portal [Beperkte <https://sip.protection.office.com/restrictedusers> gebruikers]** in het beveiligings- & compliancecentrum en de gebruiker kan geen e-mail verzenden totdat deze door een beheerder uit de portal Beperkte gebruikers is verwijderd.   Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker die dag niet meer beperkt. Zie Een gebruiker verwijderen uit de portal Beperkte gebruikers na het verzenden van [spam-e-mail](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.

     - **Geen actie, alleen waarschuwing:** e-mailmeldingen worden verzonden.

6. (Optioneel) Vouw **de sectie Automatisch doorsturen** uit om automatische doorsturen van e-mail door gebruikers naar externe afzenders te controleren. Zie Automatische externe e-mail [doorsturen in Microsoft 365](external-email-forwarding.md)voor meer informatie.

   > [!NOTE]
   >
   > - Vóór september 2020 zijn deze instellingen beschikbaar, maar niet afgedwongen.
   >
   > - Deze instellingen zijn alleen van toepassing op postvakken in de cloud.
   >
   > - Wanneer automatisch doorsturen is uitgeschakeld, ontvangt de geadresseerde een rapport over niet-bezorging (ook wel een NDR- of bouncebericht genoemd) als externe afzenders e-mail verzenden naar een postvak dat is doorgestuurd. Als het bericht wordt verzonden door een interne afzender en de doorsturenmethode postvak doorsturen [is](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd), krijgt de interne afzender de NDR.  De interne afzender krijgt geen NDR als het doorsturen is gebeurd vanwege een regel voor postvak IN.

   De beschikbare waarden zijn:

   - **Automatisch - Systeemgestuurd:** hiermee kunt u uitgaande spamfilters gebruiken om automatische doorsturen van externe e-mail te controleren. Dit is de standaardwaarde.
   - **Op**: Automatische externe e-mail doorsturen is niet uitgeschakeld door het beleid.
   - **Uit:** Alle automatische externe e-mail doorsturen is uitgeschakeld door het beleid.

7. (Vereist) Vouw de **sectie Toegepast op uit** om de interne afzenders te identificeren waar het beleid op van toepassing is.

    U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<sender1\>_ of _\<sender2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<sender1\>_ en _\<member of group 1\>_).

    Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven. U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.

    - **Het afzenderdomein is:** hiermee geeft u afzenders op in een of meer van de geconfigureerde geaccepteerde domeinen in de organisatie. Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren. Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.

    - **Afzender is:** hiermee geeft u een of meer gebruikers in uw organisatie op. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik nogmaals op **het vak Een tag toevoegen** om extra afzenders te selecteren.

    - **Afzender is lid van**: Hiermee geeft u een of meer groepen in uw organisatie op. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik nogmaals op **het vak Een tag toevoegen** om extra afzenders te selecteren.

    - **Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

8. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Gebruik het beveiligings- & compliancecentrum om uitgaand spambeleid weer te geven

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispam-instellingen** op ![ Pictogram uitvvllen ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:

   - Het standaardbeleid met de naam **Beleid voor uitgaand spamfilter**.

   - Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** aangepast **uitgaande spambeleid is.**

3. De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven of u kunt op **Beleid bewerken klikken.**

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Gebruik het beveiligings- & compliancecentrum om uitgaand spambeleid te wijzigen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispam-instellingen** op ![ Pictogram uitvvllen ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:

   - Het standaardbeleid met de naam **Beleid voor uitgaand spamfilter**.

   - Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** aangepast **uitgaande spambeleid is.**

3. Klik op **Beleid bewerken**.

Voor aangepast uitgaand spambeleid zijn de beschikbare instellingen in de flyout die wordt weergegeven identiek aan de instellingen die worden beschreven in het sectie Gebruik het [beveiligings- & compliancecentrum](#use-the-security--compliance-center-to-create-outbound-spam-policies) om uitgaand spambeleid te maken.

Voor het standaardbeleid voor uitgaande spam met  de naam Beleid voor uitgaand **spamfilter** is de sectie Toegepast op niet beschikbaar (het beleid is van toepassing op iedereen) en kunt u de naam van het beleid niet wijzigen.

Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.

### <a name="enable-or-disable-outbound-spam-policies"></a>Uitgaand spambeleid in- of uitschakelen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispam-instellingen** op Pictogram uitvvuilen om een aangepast beleid uit te vouwen dat u hebt gemaakt (de waarde in de kolom Type ![ is Aangepast uitgaande ](../../media/scc-expand-icon.png) **spambeleid).** 

3. Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.

   Verplaats te wisselknop naar links om het beleid uit te schakelen: ![Uitschakelen](../../media/scc-toggle-off.png)

   Verplaats te wisselknop naar rechts om het beleid in te schakelen: ![Inschakelen](../../media/scc-toggle-on.png)

U kunt het standaardbeleid voor uitgaande spam niet uitschakelen.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>De prioriteit instellen van aangepaste beleidsregels voor uitgaande spam

Uitgaande spambeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere agenten hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Aangepaste uitgaande spambeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0). Het standaardbeleid voor uitgaande spam met de naam Beleid voor **uitgaand spamfilter** heeft de prioriteitswaarde **Laag** en u kunt het niet wijzigen.

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Zoek op **de pagina Antispam-instellingen** het beleid waarbij de waarde in de kolom **Type** aangepast **uitgaande spambeleid is.** Let op de waarden in de kolom **Prioriteit**:

   - Het aangepaste uitgaande spambeleid met de hoogste prioriteit heeft de waarde ![ Pijl-omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Het aangepaste uitgaande spambeleid met de laagste prioriteit heeft de waarde Pijl-omhoog ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **pictogram n** (bijvoorbeeld Pijl-omhoog ![ pictogram ](../../media/ITPro-EAC-UpArrowIcon.png) **3).**

   - Als u drie of meer aangepaste uitgaande spambeleidsregels hebt, hebben de beleidsregels tussen de hoogste en laagste prioriteit de waarden Pijl-omhoog pictogram Pijl-omlaag n (bijvoorbeeld pijl-omhoog pictogram Pijl-omlaag ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ pictogram ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2).**

3. Klik op ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) of ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) om het aangepaste uitgaande spambeleid omhoog of omlaag in de prioriteitenlijst te verplaatsen.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Gebruik het beveiligings- & compliancecentrum om uitgaand spambeleid te verwijderen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispam-instellingen** op Pictogram uitvvuilen om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom Type ![ is Aangepast uitgaande ](../../media/scc-expand-icon.png) **spambeleid).** 

3. Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.

4. Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om uitgaand spambeleid te configureren

Zoals eerder beschreven, bestaat een uitgaand spambeleid uit een uitgaand spamfilterbeleid en een regel voor uitgaand spamfilter.

In Exchange Online PowerShell of zelfstandige EOP PowerShell is het verschil tussen beleidsregels voor uitgaand spamfilter en regels voor uitgaand spamfilter duidelijk. U beheert beleidsregels voor uitgaande spamfilters met de **\* cmdlets -HostedOutboundSpamFilterPolicy** en u beheert regels voor uitgaande spamfilters met de **\* cmdlets -HostedOutboundSpamFilterRule.**

- In PowerShell maakt u eerst het beleid voor uitgaand spamfilter en vervolgens maakt u de regel voor uitgaand spamfilter waarin het beleid wordt aangegeven waar de regel op van toepassing is.
- In PowerShell wijzigt u de instellingen in het beleid voor uitgaand spamfilter en de regel voor uitgaand spamfilter afzonderlijk.
- Wanneer u een beleid voor uitgaand spamfilter uit PowerShell verwijdert, wordt de bijbehorende regel voor uitgaand spamfilter niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell gebruiken om uitgaand spambeleid te maken

Het maken van een uitgaand spambeleid in PowerShell is een proces in twee stappen:

1. Maak het beleid voor uitgaand spamfilter.
2. Maak de regel voor uitgaande spamfilters die het beleid voor uitgaand spamfilter aangeeft waar de regel op van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe regel voor uitgaand spamfilter maken en er een bestaand, niet-verbonden beleid voor uitgaand spamfilter aan toewijzen. Een regel voor uitgaand spamfilter kan niet worden gekoppeld aan meer dan één beleid voor uitgaand spamfilter.

- U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor uitgaand spamfilter in PowerShell die pas beschikbaar zijn in het Beveiligings- & Compliancecentrum nadat u het beleid hebt gemaakt:

  - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ de `$false` cmdlet **New-HostedOutboundSpamFilterRule).**
  - Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ op de _\<Number\>_ **cmdlet New-HostedOutboundSpamFilterRule).**

- Een nieuw beleid voor uitgaand spamfilter dat u in PowerShell maakt, is pas zichtbaar in het Beveiligings- & Compliancecentrum als u het beleid aan een spamfilterregel toewijst.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Stap 1: PowerShell gebruiken om een beleid voor uitgaand spamfilter te maken

Als u een beleid voor uitgaand spamfilter wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In dit voorbeeld wordt een nieuw beleid voor uitgaand spamfilter met de naam Contoso Executives gemaakt met de volgende instellingen:

- De limieten voor het aantal geadresseerden zijn beperkt tot kleinere waarden die standaard worden gebruikt. Zie Limieten verzenden [voor Microsoft 365-opties](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)voor meer informatie.

- Nadat een van de limieten is bereikt, kan de gebruiker geen berichten meer verzenden.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Zie [New-HostedOutboundSpamFilterPolicy voor](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)gedetailleerde syntaxis- en parametergegevens.

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Stap 2: PowerShell gebruiken om een regel voor uitgaand spamfilter te maken

Als u een regel voor uitgaand spamfilter wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een nieuwe regel voor uitgaand spamfilter met de naam Contoso Executives gemaakt met de volgende instellingen:

- Het beleid voor uitgaand spamfilter met de naam Contoso Executives is gekoppeld aan de regel.
- De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

Zie [New-HostedOutboundSpamFilterRule voor](/powershell/module/exchange/new-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell gebruiken om uitgaand spamfilterbeleid weer te geven

Voer deze opdracht uit als u een overzichtslijst met alle beleidsregels voor uitgaand spamfilter wilt retourneren:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Als u gedetailleerde informatie wilt retourneren over een specifiek beleid voor uitgaand spamfilter, gebruikt u de volgende syntaxis:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

Dit voorbeeld retourneert alle eigenschapswaarden voor het uitgaande spamfilterbeleid met de naam Leidinggevenden.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterPolicy (Get-HostedOutboundSpamFilterPolicy)](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters weer te geven

Als u bestaande regels voor uitgaand spamfilter wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Voer deze opdracht uit als u een overzichtslijst met alle regels voor uitgaand spamfilter wilt retourneren:

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

Als u gedetailleerde informatie wilt retourneren over een specifieke regel voor uitgaand spamfilter, gebruikt u de volgende syntaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In dit voorbeeld worden alle eigenschapswaarden voor de regel voor uitgaand spamfilter met de naam Contoso Executives als retourneert.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterRule voor](/powershell/module/exchange/get-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell gebruiken om beleidsregels voor uitgaand spamfilter te wijzigen

Dezelfde instellingen zijn beschikbaar wanneer u een malwarefilterbeleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap [1: PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) gebruiken om eerder in dit artikel een sectie voor uitgaand spamfilterbeleid te maken.

> [!NOTE]
> U kunt de naam van een uitgaand spamfilterbeleid niet wijzigen (de cmdlet **Set-HostedOutboundSpamFilterPolicy** heeft _geen naamparameter)._ Wanneer u de naam van een uitgaand spambeleid wijzigt in het Beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de regel voor uitgaand _spamfilter._

Als u een beleid voor uitgaand spamfilter wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-HostedOutboundSpamFilterPolicy (Set-HostedOutboundSpamFilterPolicy)](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters te wijzigen

De enige instelling die niet beschikbaar is wanneer u een regel voor uitgaand spamfilter in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor uitgaand spamfilter wilt in- of uitschakelen.

Anders zijn er geen extra instellingen beschikbaar wanneer u een regel voor uitgaand spamfilter in PowerShell wijzigt. Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) gebruiken om eerder in dit artikel een sectie voor uitgaand spamfilter te maken.

Als u een regel voor uitgaand spamfilter wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Zie [Set-HostedOutboundSpamFilterRule voor](/powershell/module/exchange/set-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters in of uit te schakelen

Als u een regel voor uitgaand spamfilter in PowerShell in- of uitschakelen, wordt het hele uitgaande spambeleid (de regel voor uitgaand spamfilter en het toegewezen beleid voor uitgaand spamfilter) in- of uitgeschakeld. U kunt het standaardbeleid voor uitgaande spam niet in- of uitschakelen (dit beleid wordt altijd toegepast op alle geadresseerden).

Als u een uitgaande spamfilterregel in PowerShell wilt in- of uitschakelen, gebruikt u de volgende syntaxis:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de regel voor uitgaand spamfilter met de naam Marketingafdeling uitgeschakeld.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [Enable-HostedOutboundSpamFilterRule and Disable-HostedOutboundSpamFilterRule (Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) en [Disable-HostedOutboundSpamFilterRule)](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell gebruiken om de prioriteit in te stellen van regels voor uitgaande spamfilters

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Gebruik de volgende syntaxis om de prioriteit in te stellen van een uitgaande spamfilterregel in PowerShell:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u de parameter _Prioriteit_ op de cmdlet **New-HostedOutboundSpamFilterRule.**
>
> - Het standaardbeleid voor uitgaand spamfilter heeft geen bijbehorende spamfilterregel en heeft altijd de onmodifieerbare prioriteitswaarde **Laag**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell gebruiken om beleidsregels voor uitgaand spamfilter te verwijderen

Wanneer u PowerShell gebruikt om een beleid voor uitgaand spamfilter te verwijderen, wordt de bijbehorende regel voor uitgaand spamfilter niet verwijderd.

Als u een beleid voor uitgaand spamfilter in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het beleid voor uitgaand spamfilter met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Zie [Remove-HostedOutboundSpamFilterPolicy (Remove-HostedOutboundSpamFilterPolicy)](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaand spamfilter te verwijderen

Wanneer u PowerShell gebruikt om een uitgaande spamfilterregel te verwijderen, wordt het bijbehorende beleid voor uitgaand spamfilter niet verwijderd.

Als u een regel voor uitgaand spamfilter in PowerShell wilt verwijderen, gebruikt u de volgende syntaxis:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de regel voor uitgaand spamfilter met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [Remove-HostedOutboundSpamFilterRule (Remove-HostedOutboundSpamFilterRule)](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parametergegevens.

## <a name="for-more-information"></a>Voor meer informatie

[Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten](removing-user-from-restricted-users-portal-after-spam.md)

[Groep met verhoogd risico voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md)

[Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.yml)

[Rapport over automatisch doorgestuurde berichten](mfi-auto-forwarded-messages-report.md)