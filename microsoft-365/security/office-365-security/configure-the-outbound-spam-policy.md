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
ms.openlocfilehash: 9dadea740267225ff2df316b96ba7ccef92fe01e
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933129"
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

U kunt uitgaand spambeleid configureren in de Microsoft 365 Microsoft 365 Defender-portal of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

De basiselementen van een uitgaand spambeleid in EOP zijn:

- **Het beleid voor uitgaand spamfilter:** geeft de acties voor uitgaande spamfilters en de meldingsopties op.
- **De regel voor uitgaand spamfilter:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een uitgaand spamfilterbeleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spam polices beheert in de Microsoft 365 Defender portal:

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

- U opent de Microsoft 365 Defender-portal bij <https://security.microsoft.com>. Gebruik <https://security.microsoft.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

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

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a>Gebruik de Microsoft 365 Defender-portal om uitgaand spambeleid te maken

Als u een aangepast uitgaand spambeleid maakt in de Microsoft 365 Defender-portal, worden de filterregel voor spam en het bijbehorende spamfilterbeleid tegelijkertijd met dezelfde naam voor beide gemaakt.

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispambeleid** op Pictogram Maken Beleid maken en selecteer vervolgens ![ ](../../media/m365-cc-sc-create-icon.png)  **Uitgaand** in de vervolgkeuzelijst.

3. De wizard van het beleid wordt geopend. Configureer de volgende instellingen op de pagina **Uw beleid een naam geven**:
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

5. Configureer **de volgende** instellingen op de pagina Beveiligingsinstellingen die wordt geopend:
   - **Berichtlimieten:** De instellingen in deze sectie configureren de limieten voor uitgaande e-mailberichten **uit Exchange Online** postvakken:
     - **Een externe berichtlimiet instellen:** het maximum aantal externe geadresseerden per uur.
     - **Een interne berichtlimiet instellen:** het maximum aantal interne geadresseerden per uur.
     - **Een dagelijkse berichtlimiet instellen:** het maximumtotaal aantal geadresseerden per dag.

     Een geldige waarde is 0 tot 10000. De standaardwaarde is 0, wat betekent dat de service-standaardwaarden worden gebruikt. Zie Limieten verzenden [voor meer informatie.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

    Voer een waarde in het vak in of gebruik de pijlen voor het vergroten/verlagen van het vak.

   - **Beperking voor gebruikers die de berichtlimiet** bereiken: Selecteer een actie in de  vervolgkeuzelijst wanneer een van de limieten in de sectie Beveiligingsinstellingen wordt overschreden.

     Voor alle acties ontvangen de geadresseerden die in de gebruiker zijn opgegeven, geen e-mailwaarschuwingsbeleid meer (en in het nu redundante Bericht deze gebruikers en groepen als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spam** later op deze pagina) e-mailmeldingen ontvangen. 

     - **De gebruiker beperken van het verzenden van e-mail tot de volgende dag:** dit is de standaardwaarde. Er worden e-mailmeldingen verzonden en de gebruiker kan geen berichten meer verzenden tot de volgende dag, op basis van UTC-tijd. De beheerder kan dit blok niet overschrijven.
       - De activiteitswaarschuwing **met de naam Gebruiker die geen e-mail** mag verzenden, meldt beheerders (via e-mail en op de pagina **Waarschuwingen** weergeven).
       - Geadresseerden die zijn opgegeven in de instelling Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spam** in het beleid, worden ook op de hoogte gesteld.
       - De gebruiker kan geen berichten meer verzenden tot de volgende dag, op basis van UTC-tijd. De beheerder kan dit blok niet overschrijven.
     - De gebruiker beperken van het verzenden van e-mail:  e-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan Beperkte gebruikers in de Microsoft 365 Defender-portal en de gebruiker kan geen e-mail verzenden totdat deze door een beheerder is verwijderd uit beperkte <https://security.microsoft.com/restrictedusers> gebruikers.  Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker die dag niet meer beperkt. Zie Een gebruiker verwijderen uit de portal Beperkte gebruikers na het verzenden van [spam-e-mail](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.
     - **Geen actie, alleen waarschuwing:** e-mailmeldingen worden verzonden.

   - **Regels voor doorsturen:** Gebruik de instellingen in deze sectie om automatische doorsturen van e-mail door postvakken Exchange Online **externe** afzenders te beheren. Zie Automatische externe e-mail doorsturen [in](external-email-forwarding.md)Microsoft 365.

     > [!NOTE]
     > Wanneer automatisch doorsturen is uitgeschakeld, ontvangt de geadresseerde een rapport over niet-bezorging (ook wel een NDR- of bouncebericht genoemd) als externe afzenders e-mail verzenden naar een postvak dat is doorgestuurd. Als het bericht wordt verzonden door een interne afzender en de doorsturenmethode postvak doorsturen [is](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd), krijgt de interne afzender de NDR.  De interne afzender krijgt geen NDR als het doorsturen is gebeurd vanwege een regel voor postvak IN.

     Selecteer een van de volgende acties in de vervolgkeuzelijst Regels **voor** automatisch doorsturen:

     - **Automatisch - Systeemgestuurd:** hiermee kunt u uitgaande spamfilters gebruiken om automatische doorsturen van externe e-mail te controleren. Dit is de standaardwaarde.
     - **Op**: Automatische externe e-mail doorsturen is niet uitgeschakeld door het beleid.
     - **Uit:** Alle automatische externe e-mail doorsturen is uitgeschakeld door het beleid.

   - **Meldingen:** Gebruik de instellingen in de sectie om extra geadresseerden te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:

     - **Een kopie verzenden van verdachte uitgaande** personen die deze limieten overschrijden voor deze gebruikers en groepen: met deze instelling worden de opgegeven geadresseerden toegevoegd aan het BCC-veld met verdachte uitgaande berichten.

       > [!NOTE]
       > Deze instelling werkt alleen in het standaardbeleid voor uitgaande spam. Het werkt niet in aangepaste uitgaande spambeleidsregels die u maakt.

       Schakel het selectievakje in om deze instelling in te stellen. Klik in het vak dat wordt weergegeven in het vak, voer een geldig e-mailadres in en druk vervolgens op Enter of selecteer de volledige waarde die onder het vak wordt weergegeven.

       Herhaal deze stap zo vaak als nodig is. Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

   - **Informeer deze gebruikers en groepen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam**

     > [!IMPORTANT]
     >
     > - Deze instelling wordt momenteel verwijderd uit uitgaand spambeleid.
     >
     > - Het [](../../compliance/alert-policies.md) standaardwaarschuwingsbeleid met de naam **Gebruiker** die geen e-mail mag verzenden, verzendt al e-mailmeldingen naar leden van de **groep TenantAdmins** **(Globale** beheerders) wanneer gebruikers worden geblokkeerd vanwege het overschrijden van de limieten in de sectie Geadresseerdenlimieten.  **We raden u ten zeerste aan het waarschuwingsbeleid** te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers op de hoogte te stellen. Zie De [waarschuwingsinstellingen voor](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)beperkte gebruikers controleren voor instructies.

   Wanneer u gereed bent, klikt u op **Volgende**.

6. Controleer uw instellingen op de pagina **Controleren** die wordt weergegeven. U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen. U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.

   Klik op **Maken** wanneer u gereed bent.

7. Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a>Gebruik de Microsoft 365 Defender-portal om uitgaand spambeleid te bekijken

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Zoek op de pagina **Antispambeleid** een van de volgende waarden:
   - De **waarde Type** is Aangepast uitgaande **spambeleid**
   - De **waarde Naam** is **uitgaand beleid antispam (standaard)**

   De volgende eigenschappen worden weergegeven in de lijst met antispambeleidsregels:

   - **Naam**
   - **Status**
   - **Prioriteit**
   - **Type**

3. Wanneer u een uitgaand spambeleid selecteert door op de naam te klikken, worden de beleidsinstellingen weergegeven in een flyout.

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a>Gebruik de Microsoft 365 Defender-portal om uitgaand spambeleid te wijzigen

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Selecteer op **de pagina Anti-spambeleid** een uitgaand spambeleid in de lijst door op de naam te klikken:
   - Een aangepast beleid dat u hebt gemaakt waarbij de waarde in de kolom **Type** aangepast **uitgaande spambeleid is.**
   - Het standaardbeleid met de naam **Anti-spam uitgaande beleid (standaard)**.

3. U kunt in de flyout met beleidsdetails in elke sectie de optie **Bewerken** selecteren om de instellingen in de sectie te wijzigen. Zie voor meer informatie over de instellingen de vorige Portal Microsoft 365 Defender gebruiken om de sectie [uitgaand spambeleid](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies) te maken in dit artikel.

   Voor het standaardbeleid voor  uitgaande spam is de sectie Toegepast op niet beschikbaar (het beleid is van toepassing op iedereen) en kunt u de naam van het beleid niet wijzigen.

Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>Aangepaste beleidsregels voor uitgaande spam in- of uitschakelen

U kunt het standaardbeleid voor uitgaande spam niet uitschakelen.

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Selecteer op **de pagina Antispambeleid** een beleid met de **waarde Type** van Aangepast uitgaande **spambeleid** in de lijst door op de naam te klikken.

3. Boven aan de flyout met beleidsdetails die wordt weergegeven, ziet u een van de volgende waarden:
   - **Beleid uitgeschakeld**: als u het beleid wilt inschakelen, klikt u op ![Pictogram inschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Inschakelen** .
   - **Beleid ingeschakeld**: als u het beleid wilt uitschakelen, klikt u op ![Pictogram uitschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Uitschakelen**.

4. Klik in het bevestigingsvenster dat wordt weergegeven op **Inschakelen** of **Uitschakelen**.

5. Klik in de flyout met beleidsdetails op **Sluiten**.

Op de hoofdbeleidspagina wordt de waarde **Status** van het beleid weergegeven als **Ingeschakeld** of **Uitgeschakeld**.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>De prioriteit instellen van aangepaste beleidsregels voor uitgaande spam

Uitgaande spambeleidsregels krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **Prioriteitsnummer** niet rechtstreeks wijzigen in de Microsoft 365 Defender-portal). Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.

 **Opmerkingen**:

- In de Microsoft 365 Defender-portal kunt u alleen de prioriteit van het uitgaande spambeleid wijzigen nadat u deze hebt gemaakt. In PowerShell kunt u de standaardprioriteit vervangen wanneer u de spamfilterbeleidsregel maakt (die kan de prioriteit van bestaande regels beïnvloeden).
- Uitgaande spambeleidsregels worden verwerkt in de volgorde waarin ze worden weergegeven (het eerste beleid heeft de **prioriteitswaarde** 0). Het standaardbeleid voor uitgaande spam heeft de **prioriteitswaarde Laag** en u kunt deze niet wijzigen.

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Selecteer op **de pagina Antispambeleid** een beleid met de **waarde Type** van Aangepast uitgaande **spambeleid** in de lijst door op de naam te klikken.

3. Boven aan de flyout met beleidsgegevens die wordt weergegeven, ziet u **Prioriteit verhogen** of **Prioriteit verlagen** op basis van de huidige prioriteitswaarde en het aantal aangepaste beleidsregels:
   - Het uitgaande spambeleid met **prioriteitswaarde** **0** heeft alleen de **optie Prioriteit verlagen** beschikbaar.
   - Het uitgaande spambeleid met de **laagste** prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de optie **Prioriteit verhogen** beschikbaar.
   - Als u drie of meer uitgaande spambeleidsregels hebt, hebben de  beleidsregels  tussen de hoogste en laagste prioriteit zowel de opties Prioriteit verhogen als Prioriteit verlagen beschikbaar.

   Klik op het ![pictogram Prioriteit verhogen](../../media/m365-cc-sc-increase-icon.png) **Prioriteit verhogen** of ![Pictogram Prioriteit verlagen](../../media/m365-cc-sc-decrease-icon.png) **Prioriteit verlagen** om de **Prioriteitswaarde** te wijzigen.

4. Wanneer u klaar bent, klikt u in de flyout met beleidsdetails op **Sluiten**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a>Gebruik de Microsoft 365 Defender-portal om aangepaste uitgaande spambeleidsregels te verwijderen

Wanneer u de portal Microsoft 365 Defender gebruikt om een aangepast uitgaand spambeleid te verwijderen, worden de spamfilterregel en het bijbehorende spamfilterbeleid beide verwijderd. U kunt het standaardbeleid voor uitgaande spam niet verwijderen.

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Selecteer op **de pagina Antispambeleid** een beleid met de **waarde Type** van Aangepast uitgaande **spambeleid** in de lijst door op de naam te klikken. Klik boven aan de flyout met beleidsdetails die wordt weergegeven, op het ![pictogram Meer acties](../../media/m365-cc-sc-more-actions-icon.png) **Meer acties** \> ![Pictogram Beleid verwijderen](../../media/m365-cc-sc-delete-icon.png) **Beleid verwijderen**.

3. Klik in het bevestigingsvenster dat wordt weergegeven op **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om uitgaand spambeleid te configureren

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
   - U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor uitgaand spamfilter in PowerShell die pas beschikbaar zijn in de Microsoft 365 Defender-portal nadat u het beleid hebt gemaakt:
     - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld op_ de `$false` cmdlet **New-HostedOutboundSpamFilterRule).**
     - Stel de prioriteit van het beleid in tijdens het maken _(Prioriteit)_ op de _\<Number\>_ **cmdlet New-HostedOutboundSpamFilterRule).**
   - Een nieuw beleid voor uitgaand spamfilter dat u in PowerShell maakt, is pas zichtbaar in de Microsoft 365 Defender-portal als u het beleid toewijst aan een regel voor uitgaand spamfilter.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Stap 1: PowerShell gebruiken om een beleid voor uitgaand spamfilter te maken

Als u een beleid voor uitgaand spamfilter wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In dit voorbeeld wordt een nieuw beleid voor uitgaand spamfilter met de naam Contoso Executives gemaakt met de volgende instellingen:

- De limieten voor het aantal geadresseerden zijn beperkt tot kleinere waarden die standaard worden gebruikt. Zie Limieten voor [Microsoft 365 verzenden voor meer informatie.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

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
> U kunt de naam van een uitgaand spamfilterbeleid niet wijzigen (de cmdlet **Set-HostedOutboundSpamFilterPolicy** heeft _geen naamparameter)._ Wanneer u de naam van een uitgaand spambeleid wijzigt in Microsoft 365 Defender-portal, wijzigt u alleen de naam van de regel voor uitgaand _spamfilter._

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

**Opmerkingen**:

- Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u de parameter _Prioriteit_ op de cmdlet **New-HostedOutboundSpamFilterRule.**
- Het standaardbeleid voor uitgaand spamfilter heeft geen bijbehorende spamfilterregel en heeft altijd de onmodifieerbare prioriteitswaarde **Laag**.

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
