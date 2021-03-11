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
description: Beheerders kunnen in Exchange Online Protection (EOP) lezen hoe ze uitgaande spambeleidsregels kunnen weergeven, maken, wijzigen en verwijderen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 748b274903590c5e28f34ce2fb4e65292d382cd2
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717629"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Uitgaande spamfilters configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken worden uitgaande e-mailberichten die via EOP worden verzonden, automatisch gecontroleerd op spam en ongebruikelijke verzendende activiteiten.

Uitgaande spam van een gebruiker in uw organisatie duidt meestal op een gekromd account. Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het betrouwbaarheidsniveau voor spam of SCL) en worden omgeleid via de bezorgingsgroep met hoog risico om de reputatie van de service te helpen beschermen (dat wil zeggen: zorg dat de bron-e-mailservers van Microsoft 365 niet op [ip-blokkeerlijsten](high-risk-delivery-pool-for-outbound-messages.md) staan). Beheerders worden automatisch op de hoogte gesteld van verdachte uitgaande e-mailactiviteit en geblokkeerde gebruikers via [waarschuwingsbeleid.](../../compliance/alert-policies.md)

EOP maakt gebruik van uitgaand spambeleid als onderdeel van de algehele verdediging van spam in uw organisatie. Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.

Beheerders kunnen het standaardbeleid voor uitgaande spam weergeven, bewerken en configureren (maar niet verwijderen). Voor een grotere granulatie kunt u ook aangepast beleid voor uitgaande spam maken dat van toepassing is op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U kunt uitgaand spambeleid configureren in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

De basiselementen van een uitgaand spambeleid in EOP zijn:

- **Het beleid voor het filteren van uitgaande spam:** hiermee geeft u de acties op voor uitgaande spamfilters en de meldingsopties.
- **De regel voor het filteren** van uitgaande spam: geeft de prioriteits- en geadresseerdefilters (op wie het beleid van toepassing is) op een uitgaand spamfilterbeleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spambeleid beheert in het beveiligings- & compliancecentrum:

- Wanneer u een beleid maakt, maakt u tegelijkertijd een uitgaande spamfilterregel en het bijbehorende beleid voor uitgaand spamfilter met dezelfde naam voor beide.
- Wanneer u een beleid wijzigt, worden instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld, en de geadresseerdefilters de regel voor het uitgaande spamfilter gewijzigd. Alle andere instellingen wijzigen het bijbehorende uitgaande spamfilterbeleid.
- Wanneer u een beleid verwijdert, worden de regel voor het filteren van uitgaande spam en het bijbehorende uitgaande spamfilterbeleid verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Exchange Online PowerShell of de zelfstandige [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) gebruiken om uitgaande spambeleidsregels verderop in dit artikel te configureren.

Elke organisatie heeft een ingebouwd, uitgaand spambeleid met de naam Standaard dat de volgende eigenschappen heeft:

- Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook als er geen regel voor het uitgaande spamfilter (filters voor geadresseerden) aan het beleid is gekoppeld.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Als u uitgaande spamfilters effectiever wilt maken, kunt u aangepaste beleidsregels voor uitgaande spam maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u uitgaande spambeleidsregels wilt toevoegen, wijzigen en verwijderen, moet  u lid zijn van de rollengroepen **Organisatiebeheer** of Beveiligingsbeheerder.
  - Voor alleen-lezen toegang tot uitgaand spambeleid moet u  lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie de instellingen voor uitgaand spamfilterbeleid voor EOP voor de aanbevolen instellingen voor uitgaand [spambeleid.](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)

- Het [](../../compliance/alert-policies.md) standaardbeleid voor waarschuwingen met de naam Verzenden per  e-mail is **overschreden,** patronen voor verdachte e-mails verzenden gedetecteerd en Gebruikers die het verzenden van e-mail beperken, verzenden van e-mailmeldingen al naar leden van de groep **TenantAdmins** **(globale** beheerders) over ongebruikelijke uitgaande e-mailactiviteit en geblokkeerde gebruikers vanwege uitgaande spam.  Zie De [waarschuwingsinstellingen voor gebruikers met beperkingen controleren voor meer informatie.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) U wordt aangeraden dit waarschuwingsbeleid te gebruiken in plaats van de meldingsopties voor uitgaande spam.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Het beveiligings- & voor het maken van uitgaand spambeleid

Als u een aangepast uitgaand spambeleid maakt in het beveiligings- & compliancecentrum, worden de spamfilterregel en het bijbehorende spamfilterbeleid op hetzelfde moment met dezelfde naam voor beide gemaakt.

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispaminstellingen** op **Een uitgaand beleid maken.**

3. Configureer **de volgende instellingen in** het uitgaande spamfilterbeleid dat wordt geopend:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

4. (Optioneel) Vouw de **sectie Meldingen uit** om extra gebruikers te configureren die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:

   - **Een kopie van verdachte uitgaande** e-mailberichten naar specifieke personen verzenden: met deze instelling worden de opgegeven gebruikers als BCC-geadresseerden toegevoegd aan de verdachte uitgaande berichten.

     > [!NOTE]
     > Deze instelling werkt alleen in het standaardbeleid voor uitgaande spam. Het werkt niet in aangepast uitgaand spambeleid dat u maakt.

     Deze instelling inschakelen:

     1. Schakel het selectievakje in om de instelling in te stellen.

     1. Klik **op Personen toevoegen.** In de **flyout Geadresseerden toevoegen of** verwijderen die wordt weergegeven:

     1. Voert u het e-mailadres van de afzender in. U kunt meerdere e-mailadressen opgeven, gescheiden door puntkomma's (;) of één geadresseerde per regel.

     1. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de geadresseerden toe te voegen.

        Herhaal deze stappen zo vaak als nodig is.

        De geadresseerden die u hebt toegevoegd, worden weergegeven in **de sectie Adressenlijst** op de flyout. Als u een geadresseerde wilt verwijderen, klikt ![ u op de knop ](../../media/scc-remove-icon.png) Verwijderen.

     1. Klik op **Opslaan** wanneer u gereed bent.

        Als u deze instelling wilt uitschakelen, schakelt u het selectievakje uit.

   - **Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam:**

     > [!IMPORTANT]
     >
     > - Deze instelling wordt afgeschreven van het beleid voor uitgaande spam.
     >
     > - Het [](../../compliance/alert-policies.md) standaardwaarschuwingsbeleid  met de naam Gebruiker dat geen e-mail kan verzenden, verzendt al e-mailmeldingen naar leden van de groep **TenantAdmins** **(globale** beheerders) wanneer gebruikers worden geblokkeerd omdat ze de limieten in de sectie **Limieten** voor geadresseerden overschrijden. **U wordt ten zeerste aangeraden het waarschuwingsbeleid** te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers op de hoogte te stellen. Zie De [waarschuwingsinstellingen voor gebruikers met beperkingen controleren voor instructies.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)

5. (Optioneel) Vouw de **sectie Geadresseerdenlimieten** uit om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren:

   > [!NOTE]
   > Deze instellingen zijn alleen van toepassing op postvakken in de cloud.

   - **Maximum aantal geadresseerden per gebruiker**

     Een geldige waarde is 0 tot 10.000. De standaardwaarde is 0, wat betekent dat de standaardinstellingen van de service worden gebruikt. Zie Limieten voor [verzenden voor meer informatie.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

     - **Externe uurlimiet:** het maximum aantal externe geadresseerden per uur.

     - **Interne uurlimiet:** het maximum aantal interne geadresseerden per uur.

     - **Daglimiet:** het maximum aantal geadresseerden per dag.

   - **Actie wanneer een gebruiker de bovenstaande limieten** overschrijdt: Configureer de actie die moet worden ondernomen wanneer een van de limieten voor **geadresseerden** wordt overschreden. Voor alle acties geldt dat de  geadresseerden die zijn opgegeven in de Gebruiker, het beleid voor e-mailwaarschuwingen niet kunnen verzenden (en specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam in het beleid voor uitgaande **spam),** e-mailmeldingen ontvangen.

     - **De gebruiker beperken tot het verzenden van e-mail tot** de volgende dag: dit is de standaardwaarde. Er worden e-mailmeldingen verzonden en de gebruiker kan de volgende dag op basis van UTC-tijd geen berichten meer verzenden. De beheerder kan dit blok niet overschrijven.

       - De activiteitenwaarschuwing met de **naam Gebruiker kan geen e-mailmeldingen** verzenden naar beheerders (via e-mail en op de pagina **Waarschuwingen** weergeven).

       - Geadresseerden die zijn opgegeven in de instelling Specifieke personen op de hoogte stellen als een afzender is geblokkeerd vanwege het verzenden van uitgaande **spam** in het beleid, worden ook op de hoogte gesteld.

       - De gebruiker kan de volgende dag op basis van de tijd van UTC geen berichten meer verzenden. De beheerder kan dit blok niet overschrijven.

     - De gebruiker beperken van het verzenden van e-mail: e-mailmeldingen worden verzonden, de gebruiker wordt toegevoegd aan de portal **[Beperkte gebruikers] <https://sip.protection.office.com/restrictedusers>** in het beveiligings- &-compliancecentrum en de gebruiker kan pas e-mail verzenden als de gebruiker door een beheerder uit de **portal** voor beperkte gebruikers is verwijderd. Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker die dag niet opnieuw beperkt. Zie Een gebruiker verwijderen uit de portal voor beperkte gebruikers na het verzenden van [ongewenste e-mail voor instructies.](removing-user-from-restricted-users-portal-after-spam.md)

     - **Geen actie, alleen waarschuwing:** e-mailmeldingen worden verzonden.

6. (Optioneel) Vouw **de sectie Automatisch doorsturen uit** om het automatisch doorsturen van e-mail door gebruikers naar externe afzenders te bepalen. Zie Automatische doorsturen van [externe e-mail instellen in Microsoft 365](external-email-forwarding.md)voor meer informatie.

   > [!NOTE]
   >
   > - Vóór september 2020 zijn deze instellingen beschikbaar, maar niet afgedwongen.
   >
   > - Deze instellingen gelden alleen voor postvakken in de cloud.
   >
   > - Als automatisch doorsturen is uitgeschakeld, ontvangt de geadresseerde een rapport over niet-bezorging (ook wel een NDR of niet-bezorgdbericht genoemd) als externe afzenders e-mail verzenden naar een postvak waarin doorsturen is gebruikt. Als het bericht wordt verzonden door een interne afzender en de doorsturenmethode bestaat uit het doorsturen van postvakken [(ook](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) wel _SMTP-doorsturen_ genoemd), krijgt de interne afzender de NDR.  De interne afzender krijgt geen NDR als het doorsturen is veroorzaakt door een regel voor Postvak IN.

   De beschikbare waarden zijn:

   - **Automatisch - Systeembeheer:** hiermee kunt u uitgaande spam filteren om automatische doorsturen van externe e-mail te controleren. Dit is de standaardwaarde.
   - **In:** automatisch extern doorsturen van e-mail wordt niet uitgeschakeld door het beleid.
   - **Uit:** alle automatische externe doorsturen van e-mail wordt uitgeschakeld door het beleid.

7. (Vereist) Vouw de **sectie Toegepast op** uit om de interne afzenders te identificeren op wie het beleid van toepassing is.

    U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<sender1\>_ of _\<sender2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<sender1\>_ en _\<member of group 1\>_).

    Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven. U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.

    - **Het domein van de** afzender is: hiermee geeft u afzenders op in een of meer geconfigureerde geaccepteerde domeinen in de organisatie. Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren. Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.

    - **Afzender is:** geeft een of meer gebruikers in uw organisatie aan. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik nogmaals op **het vak Een tag toevoegen** om extra afzenders te selecteren.

    - **Afzender is lid van:** geeft een of meer groepen in uw organisatie aan. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik nogmaals op **het vak Een tag toevoegen** om extra afzenders te selecteren.

    - **Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

8. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Het beveiligings- & voor het bekijken van uitgaand spambeleid

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispaminstellingen** op ![ het pictogram Uitvbreken ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:

   - Het standaardbeleid met de **naam Uitgaand spamfilterbeleid.**

   - Een aangepast beleid dat u hebt gemaakt, waarbij de waarde in de **kolom Type** aangepast **uitgaand spambeleid is.**

3. De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven of u kunt op **Beleid bewerken klikken.**

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Het beveiligings- & voor het aanpassen van uitgaand spambeleid

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispaminstellingen** op ![ het pictogram Uitvbreken ](../../media/scc-expand-icon.png) om een uitgaand spambeleid uit te vouwen:

   - Het standaardbeleid met de **naam Uitgaand spamfilterbeleid.**

   - Een aangepast beleid dat u hebt gemaakt, waarbij de waarde in de **kolom Type** aangepast **uitgaand spambeleid is.**

3. Klik op **Beleid bewerken**.

Voor aangepast uitgaand spambeleid zijn de beschikbare instellingen in de flyout die wordt weergegeven identiek aan de instellingen die worden beschreven in het [beveiligings- &-compliancecentrum](#use-the-security--compliance-center-to-create-outbound-spam-policies) om de sectie Uitgaand spambeleid te maken.

Voor het standaard beleid voor uitgaande spam,  het filterbeleid voor **uitgaande spam,** is de sectie Toegepast op niet beschikbaar (het beleid geldt voor iedereen) en kunt u de naam van het beleid niet wijzigen.

Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.

### <a name="enable-or-disable-outbound-spam-policies"></a>Uitgaand spambeleid in- of uitschakelen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispaminstellingen** op het pictogram Uitviekken om een aangepast beleid dat u hebt gemaakt uit te vouwen (de waarde in de kolom Type is Aangepast ![ beleid voor uitgaande ](../../media/scc-expand-icon.png) **spam).** 

3. Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.

   Verplaats te wisselknop naar links om het beleid uit te schakelen: ![Uitschakelen](../../media/scc-toggle-off.png)

   Verplaats te wisselknop naar rechts om het beleid in te schakelen: ![Inschakelen](../../media/scc-toggle-on.png)

U kunt het standaardbeleid voor uitgaande spam niet uitschakelen.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>De prioriteit instellen van aangepast beleid voor uitgaande spam

Standaard krijgen uitgaande spambeleidsregels een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Aangepaste uitgaande spambeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid **heeft** de prioriteitswaarde 0). Het standaardbeleid voor uitgaande spam met de naam  **Uitgaand spamfilterbeleid** heeft de laagste prioriteit en u kunt dit niet wijzigen.

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit** snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Zoek op **de pagina met antispaminstellingen** het beleid waarbij de waarde in de kolom **Type** Aangepast uitgaande **spambeleid is.** Let op de waarden in de kolom **Prioriteit**:

   - Het aangepaste uitgaande spambeleid met de hoogste prioriteit heeft de waarde ![ Pijl-omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **pictogram 0.**

   - Het aangepaste uitgaande spambeleid met de laagste prioriteit heeft de waarde Pijl-omhoog ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **(bijvoorbeeld** ![ Pijl-omhoog pictogram ](../../media/ITPro-EAC-UpArrowIcon.png) **3).**

   - Als u drie of meer aangepaste uitgaande spambeleidsregels hebt, hebben de beleidsregels tussen de hoogste en laagste prioriteit de waarden Pijl-omhoog of Pijl-omlaag pictogram n (bijvoorbeeld Pijl-omhoog pictogram ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  Pijl-omlaag ![ pictogram ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2).**

3. Klik op ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) of ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) om het aangepaste uitgaande spambeleid omhoog of omlaag in de prioriteitlijst te verplaatsen.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Het beveiligings- & voor het verwijderen van uitgaand spambeleid

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op **de pagina Antispaminstellingen** op het pictogram Uitviekken om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom Type is aangepast beleid voor ![ uitgaande ](../../media/scc-expand-icon.png) **spam).** 

3. Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.

4. Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om uitgaand spambeleid te configureren

Zoals eerder is beschreven, bestaat een uitgaand spambeleid uit een beleid voor een uitgaande spamfilter en een regel voor het filteren van uitgaande spam.

In Exchange Online PowerShell of zelfstandige EOP PowerShell is het verschil tussen beleidsregels voor uitgaande spamfilters en regels voor uitgaande spamfilters duidelijk. U beheert beleidsregels voor uitgaande spamfilters met behulp van de cmdlets **\* -HostedOutboundSpamFilterPolicy** en u beheert regels voor uitgaande spamfilters met behulp van de cmdlets **\* -HostedOutboundSpamFilterRule.**

- In PowerShell maakt u eerst het uitgaande spamfilterbeleid en vervolgens maakt u de regel voor het uitgaande spamfilter die het beleid identificeert dat door de regel wordt toegepast.
- In PowerShell wijzigt u de instellingen in het beleid van het uitgaande spamfilter en de regel voor het uitgaande spamfilter afzonderlijk.
- Wanneer u een uitgaand spamfilterbeleid uit PowerShell verwijdert, wordt de bijbehorende regel voor het filteren van uitgaande spam niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell gebruiken om uitgaand spambeleid te maken

Het maken van een uitgaand spambeleid in PowerShell bestaat uit twee stappen:

1. Maak het beleid voor uitgaande spamfilters.
2. Maak de regel voor het filteren van uitgaande spam die het beleid voor het filteren van uitgaande spam aangeeft dat de regel van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe regel voor uitgaand spamfilter maken en er een bestaand, niet-verbonden beleid voor uitgaande spam aan toewijzen. Een uitgaande spamfilterregel kan niet worden gekoppeld aan meer dan één uitgaand spamfilterbeleid.

- U kunt de volgende instellingen configureren voor nieuw beleid voor uitgaande spamfilters in PowerShell die pas beschikbaar zijn in het beveiligings- & compliancecentrum nadat u het beleid hebt gemaakt:

  - Het nieuwe beleid maken dat is uitgeschakeld _(ingeschakeld_ op de `$false` cmdlet **New-HostedOutboundSpamFilterRule).**
  - De prioriteit van het beleid instellen tijdens het maken _(prioriteit)_ _\<Number\>_ op de cmdlet **New-HostedOutboundSpamFilterRule).**

- Een nieuw uitgaand spamfilterbeleid dat u in PowerShell maakt, is pas zichtbaar in het beveiligings- & compliancecentrum wanneer u het beleid toewijst aan een spamfilterregel.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Stap 1: PowerShell gebruiken om een beleid voor uitgaande spamfilters te maken

Gebruik de volgende syntaxis om een uitgaand spamfilterbeleid te maken:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In dit voorbeeld wordt een nieuw uitgaand spamfilterbeleid gemaakt met de naam Contoso-leidinggevenden met de volgende instellingen:

- De limieten voor de geadresseerden zijn beperkt tot kleinere waarden die standaard worden gebruikt. Zie Limieten voor verzenden [in microsoft 365-opties voor meer informatie.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

- Wanneer een van de limieten is bereikt, kan de gebruiker geen berichten verzenden.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Zie [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Stap 2: PowerShell gebruiken om een uitgaande spamfilterregel te maken

Gebruik de volgende syntaxis om een uitgaande spamfilterregel te maken:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een nieuwe uitgaande spamfilterregel gemaakt met de naam Contoso-leidinggevenden met de volgende instellingen:

- Het beleid van het uitgaande spamfilter met de naam Contoso Leidinggevenden wordt aan de regel gekoppeld.
- De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

Zie [New-HostedOutboundSpamFilterRule voor](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell gebruiken om beleidsregels voor uitgaande spamfilters weer te geven

Voer deze opdracht uit om een overzichtslijst met alle uitgaande spamfilterbeleidsregels te retourneren:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Gebruik de volgende syntaxis om gedetailleerde informatie over een specifiek beleid voor uitgaand spamfilter te retourneren:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In dit voorbeeld worden alle eigenschapswaarden voor het uitgaande spamfilterbeleid met de naam Leidinggevenden als retourneert.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters weer te geven

Gebruik de volgende syntaxis om bestaande regels voor uitgaande spamfilters te bekijken:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Voer deze opdracht uit om een overzichtslijst met alle regels voor het filteren van uitgaande spam te retourneren:

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

Gebruik deze syntaxis als u gedetailleerde informatie wilt retourneren over een specifieke regel voor een uitgaand spamfilter:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In dit voorbeeld worden alle eigenschapswaarden voor de uitgaande spamfilterregel met de naam Contoso Leidinggevenden als retourneert.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell gebruiken om beleid voor uitgaande spamfilters te wijzigen

Dezelfde instellingen zijn beschikbaar wanneer u een malwarefilterbeleid in PowerShell wijzigt als wanneer u het beleid maakt, zoals beschreven in stap [1: Gebruik PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) om een sectie voor uitgaand spamfilterbeleid eerder in dit artikel te maken.

> [!NOTE]
> U kunt de naam van een uitgaand spamfilterbeleid niet wijzigen (de cmdlet **Set HostedOutboundSpamFilterPolicy** heeft _geen naamparameter)._ Wanneer u de naam van een uitgaand spambeleid wijzigt in het beveiligings- & compliancecentrum, wijzigt u alleen de naam van de regel voor het uitgaande _spamfilter._

Gebruik de volgende syntaxis om een uitgaand spamfilterbeleid te wijzigen:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set HostedOutboundSpamFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters te wijzigen

De enige instelling die niet beschikbaar is wanneer u een regel voor een uitgaand spamfilter in PowerShell wijzigt, is de parameter _Enabled_ waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor uitgaande spamfilters wilt in- of uitschakelen.

Anders zijn er geen extra instellingen beschikbaar wanneer u een uitgaande spamfilterregel in PowerShell wijzigt. Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt, zoals beschreven in stap [2: PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) gebruiken om een sectie voor een uitgaande spamfilterregel eerder in dit artikel te maken.

Gebruik de volgende syntaxis om een uitgaande spamfilterregel te wijzigen:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Zie [Set HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters in of uit te schakelen

Door een uitgaande spamfilterregel in PowerShell in of uit te schakelen, schakelt u het hele uitgaande spambeleid (de regel voor het uitgaande spamfilter en het toegewezen uitgaande spamfilterbeleid) in of uit. U kunt het standaardbeleid voor uitgaande spam niet in- of uitschakelen (dit wordt altijd toegepast op alle geadresseerden).

Gebruik de volgende syntaxis om een regel voor een uitgaand spamfilter in PowerShell in of uit te schakelen:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de regel voor het filteren van uitgaande spam met de naam Marketingafdeling uitgeschakeld.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) en [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell gebruiken om de prioriteit van regels voor uitgaande spamfilters in te stellen

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
> - Als u de prioriteit van een nieuwe regel wilt instellen wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ op de cmdlet **New HostedOutboundSpamFilterRule.**
>
> - Het uitgaande standaardfilterbeleid voor ongewenste e-mail heeft geen bijbehorende regel voor het filteren van ongewenste e-mail en heeft altijd de onmodifabele prioriteit **Laagste.**

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell gebruiken om beleid voor uitgaande spamfilters te verwijderen

Wanneer u PowerShell gebruikt om een uitgaand spamfilterbeleid te verwijderen, wordt de bijbehorende regel voor het filteren van uitgaande spam niet verwijderd.

Gebruik de volgende syntaxis om een uitgaand spamfilterbeleid in PowerShell te verwijderen:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het uitgaande spamfilterbeleid met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Zie [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell gebruiken om regels voor uitgaande spamfilters te verwijderen

Wanneer u PowerShell gebruikt om een uitgaande spamfilterregel te verwijderen, wordt het bijbehorende beleid voor het filteren van uitgaande spam niet verwijderd.

Gebruik de volgende syntaxis om een uitgaande regel voor het filteren van ongewenste e-mail in PowerShell te verwijderen:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de regel voor het filteren van uitgaande spam met de naam Marketingafdeling verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="for-more-information"></a>Voor meer informatie

[Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten](removing-user-from-restricted-users-portal-after-spam.md)

[Groep met verhoogd risico voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md)

[Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.md)

[Rapport over automatisch doorgestuurde berichten](mfi-auto-forwarded-messages-report.md)
