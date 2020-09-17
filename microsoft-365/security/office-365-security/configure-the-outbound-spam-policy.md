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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie lezen over het weergeven, maken, wijzigen en verwijderen van beleid voor uitgaande spam in Exchange Online Protection (EOP).
ms.openlocfilehash: ebeebe3486ad4dad926ad72509154904700e320a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949346"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Uitgaande spamfilters configureren in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken worden uitgaande e-mailberichten die zijn verzonden via EOP, automatisch gecontroleerd op spam en ongebruikelijk verzenden.

Uitgaande spam van een gebruiker in uw organisatie geeft meestal een niet-gemanipuleerd account aan. Verdachte uitgaande berichten worden gemarkeerd als spam (ongeacht het spam betrouwbaarheidsniveau of SCL) en worden gerouteerd via de groep voor [hoog risico](high-risk-delivery-pool-for-outbound-messages.md) om de reputatie van de service te helpen beschermen (dat wil zeggen dat u de e-mailservers van microsoft 365-bron uit de lijst met IP-blokken houdt). Beheerders ontvangen automatisch een melding voor verdachte uitgaande e-mail activiteit en geblokkeerde gebruikers via een [waarschuwings beleid](../../compliance/alert-policies.md).

EOP maakt gebruik van een beleid voor uitgaande spam als onderdeel van de algemene verdediging van uw organisatie tegen spam. Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.

Beheerders kunnen het standaard uitgaande spam beleid bekijken, bewerken en configureren (maar niet verwijderen). Voor een grotere nauwkeurigheid kunt u ook een aangepast beleid voor uitgaande spam maken dat geldt voor specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U kunt uitgaande spam beleidsregels configureren in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).

De basiselementen van een uitgaand spam beleid in EOP zijn:

- **Het beleid voor uitgaande spamfilters**: Hiermee wordt de actie opgegeven voor uitgaande spam filtering Verdicts en de Meldingsopties.
- Met **de regel voor uitgaande spam filtering**: geeft u de prioriteit op van de filters voor een uitgaand spamfilter (waarvoor het beleid van toepassing is).

Het verschil tussen deze twee elementen is niet duidelijk wanneer u uitgaande spam policies beheert in de beveiligings & nalevings centrum:

- Wanneer u een beleid maakt, maakt u eigenlijk een uitgaande spamfilter regel en het bijbehorende uitgaande spamfilter beleid tegelijk met dezelfde naam voor beide.
- Wanneer u een beleid wijzigt, worden de instellingen voor de regels naam, prioriteit, ingeschakeld of uitgeschakeld en de filters voor uitgaande spamfilters gewijzigd. Alle andere instellingen wijzigen het bijbehorende uitgaande spamfilter beleid.
- Wanneer u een beleid verwijdert, worden de regels uitgaande spamfilter en het bijbehorende uitgaande spamfilter verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie voor meer informatie de sectie [Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om uitgaande spam beleidsregels](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) verderop in dit onderwerp te configureren.

Elke organisatie heeft een ingebouwd spam beleid met de naam standaard met de volgende eigenschappen:

- Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen uitgaande spamfilter regel (Recipient filters) gekoppeld aan het beleid.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit dan het beleid met de naam Standaard.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Als u de efficiëntie van uitgaande spamfilters wilt verbeteren, kunt u een aangepast beleid voor uitgaande spam maken met strikte instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:

  - Als u een beleid voor uitgaande spam wilt toevoegen, wijzigen of verwijderen, moet u lid zijn van een van de volgende rollen groepen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezen toegang tot een uitgaand spam beleid moet u lid zijn van een van de volgende rollen groepen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Voor de aanbevolen instellingen voor het beleid voor uitgaande spam, raadpleegt u [beleidsinstellingen voor uitgaande spamfilters EOP](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).

- De standaard [Waarschuwingsregels](../../compliance/alert-policies.md) met de naam **e-mail limieten**voor het verzenden van e-mail zijn **verdacht en verdachte patronen**voor het verzenden van e-mail, en **gebruikers die geen e-mail verzenden** , ontvangen al e-mail meldingen naar leden van de **TenantAdmins** (**algemene beheerders**) voor ongebruikelijke uitgaande e-mail activiteit en geblokkeerde gebruikers vanwege uitgaande spam. Zie voor meer informatie [de instellingen voor meldingen voor gebruikers met beperkte toegang](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). We raden u aan dit waarschuwings beleid te gebruiken in plaats van de Meldingsopties in het beleid voor uitgaande spam.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Het nalevings centrum voor beveiliging & gebruiken om uitgaande spam beleidsregels te maken

Als u een aangepast beleid voor uitgaande spam maakt in de beveiligings & nalevings centrum, worden de regels voor spamfilter en het bijbehorende spamfilter beleid tegelijk gemaakt met dezelfde naam voor beide.

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **anti spam instellingen** op **Maak een uitgaand beleid**.

3. Configureer de volgende instellingen in het **filter beleid uitgaande spam** dat wordt geopend:

   - **Naam**: een unieke beschrijvende naam voor het beleid.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

4. Option Vouw de sectie **meldingen** uit om extra gebruikers weer te geven die kopieën en meldingen van verdachte uitgaande e-mailberichten moeten ontvangen:

   - **Een kopie van verdachte uitgaande e-mailberichten naar specifieke personen verzenden: met**deze instelling worden de opgegeven gebruikers toegevoegd als BCC-geadresseerden voor de verdachte uitgaande berichten.

     > [!NOTE]
     > Deze instelling werkt alleen met het standaardbeleid voor uitgaande spam. Het werkt niet in een aangepast uitgaand spam beleid dat u maakt.

     U schakelt deze instelling als volgt in:

     1. Schakel het selectievakje in om de instelling in te schakelen.

     1. Klik op **personen toevoegen**. In het flyout voor **geadresseerden toevoegen of verwijderen** dat wordt weergegeven:

     1. Voert u het e-mailadres van de afzender in. U kunt meerdere e-mailadressen opgeven, gescheiden door puntkomma's (;) of één geadresseerde per regel.

     1. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) geadresseerden toevoegen.

        Herhaal deze stappen zo vaak als nodig is.

        De geadresseerden die u hebt toegevoegd, worden weergegeven in de sectie **lijst met geadresseerden** in de vervolgkeuzelijst. Als u een geadresseerde wilt verwijderen, klikt u op de ![ knop verwijderen ](../../media/scc-remove-icon.png) .

     1. Klik op **Opslaan** wanneer u gereed bent.

        Als u deze instelling wilt uitschakelen, schakelt u het selectievakje uit.

   - **Specifieke personen op de hoogte stellen wanneer een afzender wordt geblokkeerd vanwege het verzenden van uitgaande spam**:

     > [!IMPORTANT]
     >
     > - Deze instelling wordt afgeschaft van uitgaande spam beleidsregels.
     >
     > - In het standaard [waarschuwings beleid](../../compliance/alert-policies.md) wordt de naam gebruiker voor het **verzenden van e-mail** al e-mail meldingen verzonden naar leden van de **TenantAdmins** (**algemene beheerders**) wanneer gebruikers worden geblokkeerd omdat ze de limieten voor de sectie **limieten** van de ontvanger overschrijden. **U wordt ten zeerste aangeraden het waarschuwings beleid te gebruiken in plaats van deze instelling in het beleid voor uitgaande spam om beheerders en andere gebruikers op de hoogte te stellen**. Zie [de instellingen voor meldingen voor gebruikers met beperkte toegang controleren](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)voor instructies.

5. Option Vouw de sectie **limieten voor geadresseerden** uit om de limieten en acties voor verdachte uitgaande e-mailberichten te configureren:

   > [!NOTE]
   > Deze instellingen zijn alleen van toepassing op postvakken op basis van de Cloud.

   - **Maximum aantal geadresseerden per gebruiker**

     Een geldige waarde is 0 tot 10000. De standaardwaarde is 0, wat betekent dat de service-standaardwaarden worden gebruikt. Zie [limieten verzenden](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)voor meer informatie.

     - **Extern uurtarief**: het maximale aantal externe geadresseerden per uur.

     - **Interne limiet voor het hele uur**: het maximale aantal interne geadresseerden per uur.

     - **Dagelijkse limiet**: het maximale aantal geadresseerden per dag.

   - **Actie wanneer een gebruiker de limieten overschrijdt**: Configureer de actie die moet worden uitgevoerd wanneer een van de **limieten** van de ontvanger wordt overschreden. Voor alle acties zijn de geadresseerden opgegeven in de gebruikers die het beleid voor het **verzenden van e-mail waarschuwingen niet verzenden** (en in de nu overbodige **specifieke personen op de hoogte gesteld als een afzender wordt geblokkeerd vanwege het verzenden van uitgaande** spam-instelling in het uitgaande spam beleid van e-mailberichten.

     - **Zorgen dat de gebruiker geen e-mail meer kan verzenden voor de volgende dag**: dit is de standaardwaarde. Er worden e-mail meldingen verzonden, en de gebruiker kan geen berichten meer naar de volgende dag verzenden, op basis van UTC-tijd. Het is niet mogelijk dat de beheerder dit blok kan overschrijven.

       - De melding met de naam **gebruiker beperkt vanwege het verzenden van e-mail** (via e-mail en op de pagina **waarschuwingen weergeven** ).

       - Geadresseerden die zijn opgegeven in het **bericht specifieke personen op de hoogte brengen van een afzender die wordt geblokkeerd vanwege het verzenden van uitgaande spam** instelling in het beleid, worden eveneens gewaarschuwd.

       - De gebruiker kan geen berichten meer naar de volgende dag verzenden, op basis van UTC-tijd. Het is niet mogelijk dat de beheerder dit blok kan overschrijven.

     - Voor **komen dat de gebruiker e-mail verzendt**: e-mail meldingen worden verzonden naar de portal **[beperkte gebruikers] <https://sip.protection.office.com/restrictedusers> ** in het beveiligings & nalevings centrum en de gebruiker kan geen e-mail verzenden totdat deze wordt verwijderd uit de portal met **beperkte gebruikers** door een beheerder. Nadat een beheerder de gebruiker uit de lijst heeft verwijderd, wordt de gebruiker niet meer voor die dag beperkt. Zie [een gebruiker verwijderen uit de portal met beperkte gebruikers na het verzenden van spamberichten](removing-user-from-restricted-users-portal-after-spam.md)voor instructies.

     - **Geen actie, alleen waarschuwingen**: e-mail meldingen worden verzonden.

6. Option Vouw **automatisch doorsturen** uit om het automatisch doorsturen van e-mail door gebruikers naar externe afzenders te regelen. Zie [doorsturen van E-mail configureren](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)voor meer informatie over automatisch doorsturen.

   > [!NOTE]
   >
   > - Vóór september 2020 zijn deze instellingen beschikbaar, maar worden deze niet afgedwongen.
   >
   > - Deze instellingen zijn alleen van toepassing op postvakken op basis van de Cloud.
   >
   > - Deze instelling geldt niet voor automatisch doorsturen naar interne geadresseerden.

   De beschikbare waarden zijn:

   - **Automatisch-door het systeem beheerde**functies: uitgaande spamfilters voor het beheren van automatisch externe e-mail doorsturen. Dit is de standaardwaarde.

   - **Ingeschakeld**: automatisch extern doorsturen van e-mail wordt niet uitgeschakeld door het beleid.

   - **Uit**: alle automatische doorsturen van e-mail is uitgeschakeld door het beleid.

7. Opgestart Vouw de sectie **toegepast op** uit om de interne afzenders op te geven waarop het beleid van toepassing is.

    U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<sender1\>_ of _\<sender2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<sender1\>_ en _\<member of group 1\>_).

    Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven. U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.

    - **Het domein van de afzender is**: verwijst naar afzenders in een of meer van de geconfigureerde domeinen in de organisatie. Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren. Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.

    - **Afzender is**: geeft een of meer gebruikers in uw organisatie aan. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik opnieuw op het vak **een tag toevoegen** om extra afzenders te selecteren.

    - **Afzender is een lid van**: geeft een of meer groepen op in uw organisatie. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik opnieuw op het vak **een tag toevoegen** om extra afzenders te selecteren.

    - **Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

8. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Het beleid voor uitgaand spam weergeven met behulp van beveiligings &

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om een uitgaand spam beleid uit te vouwen:

   - Het standaardbeleid met de naam **uitgaand spamfilter beleid**.

   - Een aangepast beleid dat u hebt gemaakt en waarvan de waarde in de kolom **type** een **aangepast uitgaand spam beleid**is.

3. De beleidsinstellingen worden weergegeven in de uitgebreide beleidsdetails die worden weergegeven, of u kunt op **beleid bewerken**klikken.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Het beleid voor de naleving van beveiligings & gebruiken om uitgaande spam beleidsregels te wijzigen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om een uitgaand spam beleid uit te vouwen:

   - Het standaardbeleid met de naam **uitgaand spamfilter beleid**.

   - Een aangepast beleid dat u hebt gemaakt en waarvan de waarde in de kolom **type** een **aangepast uitgaand spam beleid**is.

3. Klik op **Beleid bewerken**.

Voor een aangepast uitgaand spam beleid zijn de beschikbare instellingen in de vervolgmenu die worden weergegeven, identiek aan de instellingen die worden beschreven in de sectie [het hulpmiddel beveiligings & gebruiken om uitgaande spam beleidsregels te maken](#use-the-security--compliance-center-to-create-outbound-spam-policies) .

Voor het standaardbeleid voor uitgaande spam met de naam **uitgaand spamfilter beleid**is de sectie **toegepast op** niet beschikbaar (het beleid geldt voor iedereen) en kunt u de naam van het beleid niet wijzigen.

Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.

### <a name="enable-or-disable-outbound-spam-policies"></a>Beleid voor uitgaande spam in-of uitschakelen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om een aangepast beleid dat u hebt gemaakt, uit te vouwen (de waarde in de kolom **type** is **aangepast beleid voor uitgaande spam**).

3. Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.

   Verplaats te wisselknop naar links om het beleid uit te schakelen: ![Uitschakelen](../../media/scc-toggle-off.png)

   Verplaats te wisselknop naar rechts om het beleid in te schakelen: ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

U kunt het standaardbeleid voor uitgaande spam niet uitschakelen.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>De prioriteit voor aangepaste spam beleidsregels instellen

Beleidsregels voor uitgaande spam krijgen standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwe policies zijn een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Het aangepaste beleid voor uitgaande spam wordt weergegeven in de volgorde waarin ze zijn verwerkt ( **het eerste** beleid heeft de waarde 0). Het uitgaande spam beleid met de naam **uitgaand spamfilter beleid** heeft de prioriteitswaarde **laag**en u kunt deze niet wijzigen.

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit**snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Zoek op de pagina **anti spam instellingen** de beleidsregels waarvan de waarde in de kolom **type** een **aangepast uitgaand spam beleid**is. Let op de waarden in de kolom **Prioriteit**:

   - Het aangepaste beleid voor uitgaande spam met de hoogste prioriteit heeft een ![ pijl-omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Het aangepaste beleid voor uitgaande spam met de laagste prioriteit heeft het ![ pijlpictogram omhoog ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (bijvoorbeeld pijl- ![ omhoog ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Als u een aangepast uitgaand spam beleid hebt, hebben de beleidsregels tussen de hoogste en de laagste prioriteit een pijl ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ -omlaag ](../../media/ITPro-EAC-DownArrowIcon.png) **n** ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**en pijl-omlaag-pictogram omhoog

3. Klik op ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) of ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) Als u het aangepaste uitgaande spam beleid omhoog of omlaag wilt verplaatsen in de lijst prioriteit.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Het nalevings centrum voor beveiligings & gebruiken om beleid voor uitgaande spam te verwijderen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Op de pagina **anti spam instellingen** klikt u op ![ pictogram uitvouwen ](../../media/scc-expand-icon.png) om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de kolom **type** is **aangepast beleid voor uitgaande spam**).

3. Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.

4. Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Uitgaande spam beleidsregels met Exchange Online PowerShell of zelfstandige EOP PowerShell configureren

Zoals hierboven is beschreven, bestaat een uitgaand spamfilter beleid en een uitgaande spamfilter regel.

In Exchange Online PowerShell of zelfstandige EOP PowerShell wordt het verschil tussen het uitgaande spamfilter beleid en de regels voor uitgaande spam filteren duidelijk. U beheert uitgaand spamfilter beleid met behulp van de cmdlets van ** \* HostedOutboundSpamFilterPolicy** en u beheert de regels voor uitgaande spamfilter met behulp van de cmdlets van ** \* HostedOutboundSpamFilterRule** .

- In PowerShell maakt u eerst een uitgaand spamfilter beleid, en vervolgens maakt u de uitgaande spamfilter regel waarmee het beleid wordt aangegeven waarop de regel van toepassing is.
- In PowerShell wijzigt u de instellingen in het filter beleid uitgaande spam en de regel voor uitgaande spam afzonderlijk.
- Wanneer u een uitgaand spamfilter beleid uit PowerShell verwijdert, wordt de bijbehorende regel voor uitgaande spamfilters niet automatisch verwijderd en omgekeerd.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>PowerShell gebruiken om uitgaande spam beleidsregels te maken

Het maken van een beleid voor uitgaande spam in PowerShell is een procedure die bestaat uit twee stappen:

1. Het beleid voor uitgaande spamfilters maken.
2. Maak de uitgaande spamfilter regel waarmee u het uitgaande spamfilter beleid opgeeft waarop de regel van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe regel voor uitgaande spamfilters maken en een bestaand, niet-gekoppeld uitgaand spamfilter beleid toewijzen. Uitgaande spamfilter regels kunnen niet worden gekoppeld aan meer dan één uitgaand spamfilter beleid.

- U kunt de volgende instellingen configureren voor nieuwe beleidsregels voor uitgaande spam in PowerShell die niet beschikbaar zijn in het beveiligings & nalevings centrum totdat u het beleid hebt gemaakt:

  - Het nieuwe beleid maken als uitgeschakeld (_ingeschakeld_ `$false` in de **nieuwe HostedOutboundSpamFilterRule-** cmdlet).
  - De prioriteit van het beleid instellen voor het maken_Priority_ van de _\<Number\>_ **nieuwe HostedOutboundSpamFilterRule-** cmdlet (prioriteit).

- Een nieuw beleid voor het uitgaande spamfilter dat u in PowerShell maakt, is niet zichtbaar in het beveiligings & nalevings centrum tot u het beleid aan een spamfilter regel toewijst.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Stap 1: PowerShell gebruiken om een uitgaand spamfilter beleid te maken

U kunt als volgt een uitgaand spamfilter beleid maken:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In dit voorbeeld wordt een nieuw beleid voor uitgaande spam met de naam contoso-leidinggevenden gemaakt met de volgende instellingen:

- De limieten voor de snelheid van de ontvanger zijn beperkt tot kleinere waarden, namelijk de standaardwaarden. Zie limieten voor het [verzenden van alle opties in Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)voor meer informatie.

- Wanneer een van de limieten is bereikt, kan de gebruiker geen berichten verzenden.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Zie [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Stap 2: PowerShell gebruiken om een uitgaande spamfilter regel te maken

Als u een uitgaande spamfilter regel wilt maken, gebruikt u de volgende syntaxis:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In dit voorbeeld wordt een nieuwe regel voor een uitgaande spamfilter met de naam contoso leidinggevenden gemaakt met de volgende instellingen:

- Het uitgaande spamfilter beleid met de naam contoso-leidinggevenden is gekoppeld aan de regel.

- De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Zie [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>PowerShell gebruiken om uitgaand spamfilter beleid weer te geven

Voer de volgende opdracht uit als u een overzicht wilt weergeven van alle uitgaande spamfilter beleid:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Gebruik de volgende syntaxis om gedetailleerde informatie weer te geven over een specifiek beleid voor uitgaand spamfilter:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In het volgende voorbeeld worden alle eigenschapswaarden geretourneerd voor het uitgaande spamfilter beleid met de naam leidinggevenden.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>PowerShell gebruiken om uitgaande spamfilter regels weer te geven

Als u bestaande regels voor uitgaande spamfilters wilt weergeven, gebruikt u de volgende syntaxis:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Voer de volgende opdracht uit als u een overzicht wilt weergeven van alle regels voor uitgaande spamfilter:

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

Gebruik de volgende syntaxis om gedetailleerde informatie weer te geven over een specifieke regel voor uitgaande spamfilter:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In het volgende voorbeeld worden alle eigenschapwaarden voor de uitgaande spamfilter regel met de naam contoso leidinggevenden geretourneerd.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Zie [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>PowerShell gebruiken om uitgaand spamfilter beleid te wijzigen

U kunt dezelfde instellingen gebruiken als u een beleid voor het filteren van schadelijke software in PowerShell wijzigt, zoals wordt beschreven in de sectie [stap 1: PowerShell gebruiken om een uitgaand spamfilter beleid te maken](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) eerder in dit onderwerp.

> [!NOTE]
> U kunt de naam van een uitgaand spamfilter beleid niet wijzigen (de cmdlet **set-HostedOutboundSpamFilterPolicy** heeft geen _naam_ parameter). Wanneer u de naam van een uitgaand spam beleid wijzigt in de beveiligings & nalevings centrum, wordt de naam van de uitgaande spamfilter _regel_alleen gewijzigd.

Als u een uitgaand spamfilter beleid wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Zie [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>PowerShell gebruiken om uitgaande spamfilter regels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een uitgaande spamfilter regel wijzigt in PowerShell is de _ingeschakelde_ parameter waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande regels voor uitgaande spamfilters wilt in-of uitschakelen.

Anders zijn er geen extra instellingen beschikbaar wanneer u een uitgaande spamfilter regel wijzigt in PowerShell. U kunt dezelfde instellingen gebruiken wanneer u een regel maakt zoals wordt beschreven in de sectie [stap 2: PowerShell gebruiken om een uitgaande spamfilter regel te maken](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) eerder in dit onderwerp.

Als u een uitgaande spamfilter regel wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Zie [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>PowerShell gebruiken om uitgaande spamfilter regels in of uit te schakelen

Als u een uitgaande spamfilter regel in-of uitschakelt in PowerShell, wordt het volledige uitgaande spam beleid (de regels voor uitgaande spamfilter en het uitgaande spamfilter beleid) in-of uitgeschakeld. U kunt het standaardbeleid voor uitgaande spam niet in-of uitschakelen (het is altijd altijd van toepassing op alle geadresseerden).

Gebruik de volgende syntaxis om een uitgaande spamfilter regel in of uit te schakelen in PowerShell:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de uitgaande spamfilter regel genaamd marketing afdeling uitgeschakeld.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) en [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>PowerShell gebruiken voor het instellen van de prioriteit van regels voor uitgaande spamfilters

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Als u de prioriteit wilt instellen van een uitgaande spamfilter regel in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - Als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u de parameter _Priority_ op de cmdlet **New-HostedOutboundSpamFilterRule** .
>
> - Het uitgaande spamfilter beleid heeft geen corresponderende regel voor spamfilters, en het is altijd de **laagste**ongewijzigde prioriteitswaarde.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>PowerShell gebruiken om beleid voor uitgaande spamfilters te verwijderen

Wanneer u PowerShell gebruikt om een uitgaand spamfilter beleid te verwijderen, wordt de bijbehorende regel voor uitgaande spamfilter niet verwijderd.

Als u een beleid voor uitgaande spamfilters wilt verwijderen in PowerShell, gebruikt u de volgende syntaxis:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het uitgaande spamfilter beleid genaamd marketing afdeling verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Zie [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)voor gedetailleerde syntaxis-en parameterinformatie.

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>PowerShell gebruiken om uitgaande spamfilter regels te verwijderen

Wanneer u PowerShell gebruikt om een uitgaande spamfilter regel te verwijderen, wordt het bijbehorende uitgaande spamfilter beleid niet verwijderd.

Gebruik de volgende syntaxis om een uitgaande spamfilter regel te verwijderen in PowerShell:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de uitgaande spamfilter regel genaamd marketing afdeling verwijderd.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Zie [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)voor gedetailleerde syntaxis-en parameterinformatie.

## <a name="for-more-information"></a>Voor meer informatie

[Geblokkeerde gebruikers verwijderen uit de portal voor gebruikers met beperkte rechten](removing-user-from-restricted-users-portal-after-spam.md)

[Groep met verhoogd risico voor uitgaande berichten](high-risk-delivery-pool-for-outbound-messages.md)

[Veelgestelde vragen over beveiliging tegen ongewenste e-mail](anti-spam-protection-faq.md)

[Rapport over automatisch doorgestuurde berichten](mfi-auto-forwarded-messages-report.md)
