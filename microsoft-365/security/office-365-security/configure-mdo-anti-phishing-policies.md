---
title: Anti-phishingbeleid configureren in Microsoft Defender voor Office 365
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
description: Beheerders kunnen leren hoe ze geavanceerde anti-phishingbeleidsregels kunnen maken, wijzigen en verwijderen die beschikbaar zijn in organisaties met Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3660b9574f4faf4ee9c0602ac23b36f8634650dc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537905"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Anti-phishingbeleid configureren in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Anti-phishingbeleid in [Microsoft Defender voor Office 365](defender-for-office-365.md) kan uw organisatie helpen beschermen tegen kwaadaardige phishingaanvallen op basis van imitaties en andere soorten phishingaanvallen. Zie [Anti-phishingbeveiliging](anti-phishing-protection.md)voor meer informatie over de verschillen tussen anti-phishingbeleid in Exchange Online Protection (EOP) en anti-phishingbeleid in Microsoft Defender voor Office 365.

Beheerders kunnen het standaard anti-phishingbeleid weergeven, bewerken en configureren (maar niet verwijderen). Voor meer granulariteit kunt u ook aangepaste anti-phishingbeleidsregels maken die van toepassing zijn op specifieke gebruikers, groepen of domeinen in uw organisatie. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U kunt anti-phishingbeleid configureren in het Beveiligings- & compliancecentrum of in Exchange Online PowerShell.

Zie [Anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP voor informatie over het configureren van de meer beperkte anti-phishingbeleidsregels die beschikbaar zijn in Exchange Online Protection-organisaties (dat wil zeggen organisaties zonder Microsoft Defender voor Office 365).

De basiselementen van een anti-phishingbeleid zijn:

- **Het anti-phish-beleid:** geeft de phishingbeveiligingen aan die u wilt in- of uitschakelen en de acties om opties toe te passen.
- **De anti-phish-regel:** hiermee geeft u de prioriteits- en geadresseerdefilters op (op wie het beleid van toepassing is) voor een anti-phish-beleid.

Het verschil tussen deze twee elementen is niet duidelijk wanneer u anti-phishingbeleid beheert in het beveiligings- & compliancecentrum:

- Wanneer u een beleid maakt, maakt u tegelijkertijd een anti-phish-regel en het bijbehorende anti-phish-beleid met dezelfde naam voor beide.
- Wanneer u een beleid wijzigt, wijzigen instellingen met betrekking tot de naam, prioriteit, ingeschakeld of uitgeschakeld en geadresseerdefilters de anti-phish-regel. Alle andere instellingen wijzigen het bijbehorende anti-phish-beleid.
- Wanneer u een beleid verwijdert, worden de anti-phish-regel en het bijbehorende anti-phish-beleid verwijderd.

In Exchange Online PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie Use Exchange Online PowerShell to configure [anti-phishing policies in Microsoft Defender for Office 365 section verderop](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) in dit artikel voor meer informatie.

Elke Microsoft Defender voor Office 365 heeft een ingebouwd anti-phishingbeleid met de naam Office365 AntiPhish Default dat de volgende eigenschappen heeft:

- Het beleid wordt toegepast op alle geadresseerden in de organisatie, ook al is er geen anti-phish-regel (ontvangersfilters) gekoppeld aan het beleid.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Als u de effectiviteit van anti-phishingbeveiliging in Microsoft Defender voor Office 365 wilt vergroten, kunt u aangepaste anti-phishingbeleidsregels maken met striktere instellingen die worden toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **pagina Anti-phishing wilt** gaan, gebruikt u <https://protection.office.com/antiphishing> .

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u anti-phishingbeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**
  - Als u alleen-lezen toegang wilt tot anti-phishingbeleid, moet u lid zijn van de rollengroepen **Globale** lezer of  <sup>\*</sup> Beveiligingslezer.

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De **rollengroep Alleen-weergeven voor** organisatiebeheer in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezen toegang tot de <sup>\*</sup> functie.
  - <sup>\*</sup> In het & compliancecentrum kunnen gebruikers met alleen-lezen toegang de instellingen van aangepast anti-phishingbeleid bekijken. Alleen-lezen gebruikers kunnen de instellingen niet zien in het standaard anti-phishingbeleid.

- Voor onze aanbevolen instellingen voor anti-phishingbeleid in Microsoft Defender voor Office 365, zie [Anti-phishingbeleid in Defender voor Office 365 instellingen.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

- Maximaal 30 minuten toestaan dat een nieuw of bijgewerkt beleid wordt toegepast.

- Zie Bestelling en prioriteit van e-mailbeveiliging voor informatie over de toepassing van anti-phishingbeleid in de [filterpijplijn.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid te maken in Microsoft Defender voor Office 365

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
   - **Het domein van de geadresseerde is:** hiermee geeft u geadresseerden op in een of meer van de geconfigureerde geaccepteerde domeinen in de organisatie.

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

Nadat u het anti-phishingbeleid met deze algemene instellingen hebt gemaakt, gebruikt u de instructies in de volgende sectie om de beveiligingsinstellingen in het beleid te configureren.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid in Microsoft Defender te wijzigen voor Office 365

Gebruik de volgende procedures om anti-phishingbeleid te wijzigen: een nieuw beleid dat u hebt gemaakt of bestaande beleidsregels die u al hebt aangepast.

1. Als u er nog niet bent, opent u het Beveiligingscentrum & compliancecentrum en gaat u naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Selecteer het aangepaste anti-phishingbeleid dat u wilt wijzigen. Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.

3. Het **fly-out \<name\> Beleid** bewerken wordt weergegeven. Als u in **een** sectie op Bewerken klikt, hebt u toegang tot de instellingen in die sectie.

   - De volgende stappen worden weergegeven in de volgorde waarin de secties worden weergegeven, maar ze zijn niet opeenvolgend (u kunt de secties in elke volgorde selecteren en wijzigen).

   - Nadat u **in** een sectie op Bewerken hebt geklikt, worden de beschikbare instellingen weergegeven in  een wizard-indeling, maar  u kunt in elke volgorde binnen de pagina's springen en u kunt op Opslaan op een pagina klikken (of  ![ ](../../media/scc-remove-icon.png) **\<name\>** pictogram Annuleren of Sluiten sluiten om terug te keren naar de pagina Uw beleid bewerken (u hoeft niet naar de laatste pagina van de wizard te gaan om op te slaan of te verlaten).

4. **Beleidsinstelling:** Klik op **Bewerken** om dezelfde instellingen te wijzigen die beschikbaar waren toen u het [beleid](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in de vorige sectie maakte:

   - **Naam**
   - **Beschrijving**
   - **Toegepast op**
   - **Uw instellingen controleren**

   Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.

5. **Imitatie:** Klik op **Bewerken om** de beveiligde afzenders en beveiligde afzenderdomeinen in het beleid te wijzigen. Deze instellingen zijn een voorwaarde voor het beleid dat specifieke afzenders identificeert die moeten zoeken (afzonderlijk of per domein) in het Van-adres van binnenkomende berichten. Zie Instellingen voor imitatie [in anti-phishingbeleid in Microsoft Defender](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor Office 365.

   - **Gebruikers toevoegen om te beveiligen:** De standaardwaarde is  ![ ](../../media/scc-toggle-off.png) Uit-uit. Als u de knop wilt in- of uitschakelen, schuift u de schakelknop naar **Aan** en klikt u vervolgens op de knop Gebruiker ![ toevoegen die wordt ](../../media/scc-toggle-on.png) weergegeven. 

     Configureer **in het** flyout Gebruiker toevoegen dat wordt weergegeven de volgende waarden:

     - **E-mailadres**:

       - Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.
       - Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.
       - Als u een item wilt verwijderen, klikt **u op Pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) gebruiker.

     - **Naam:** Deze waarde wordt ingevuld op basis van het e-mailadres dat u hebt geselecteerd, maar u kunt deze wijzigen.

     Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.

     Als u een bestaand item wilt bewerken, selecteert u de beveiligde gebruiker in de lijst.

     > [!NOTE]
     >
     > - In elk anti-phishingbeleid kunt u maximaal 60 beveiligde gebruikers opgeven (e-mailadressen van afzenders). U kunt niet dezelfde beveiligde gebruiker opgeven in meerdere beleidsregels.
     >
     > - Gebruikersbeveiliging werkt niet als de afzender en geadresseerde eerder via e-mail hebben gecommuniceerd. Als de afzender en geadresseerde nooit via e-mail hebben gecommuniceerd, wordt het bericht geïdentificeerd als een imitatiepoging.

   - **Domeinen toevoegen om te beveiligen:** Een of beide van de volgende instellingen configureren:

     - **Automatisch de domeinen opnemen die ik bezit:** De standaardwaarde is **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen. Als u deze wilt in-  of uitschakelen, schuift u de schakelknop naar ![ In-/uitschakelen. ](../../media/scc-toggle-on.png)

       Als u de domeinen wilt weergeven die u bezit, selecteert u **Domeinen weergeven van wie ik de eigenaar ben.**

     - **Aangepaste domeinen opnemen:** De standaardwaarde is  ![ ](../../media/scc-toggle-off.png) Uitgeschakeld. Als u de knop wilt  in- of uitschakelen, schuift u de schakelknop naar Aan en typt u in het vak Domeinen toevoegen de domeinnaam ![ ](../../media/scc-toggle-on.png) (bijvoorbeeld contoso.com),  drukt u op Enter en herhaalt u dit zo nodig.

     > [!NOTE]
     > U kunt maximaal 50 domeinen hebben in alle anti-phishingbeleidsregels.

   - **Acties**: Klik op **Bewerken**

     - **Als e-mail wordt** verzonden door een nagebootsde gebruiker: Configureer een van de volgende acties voor berichten waarbij de afzender een van de beveiligde gebruikers is die u hebt opgegeven in Gebruikers toevoegen ter **bescherming:**

       - **Geen actie toepassen**
       - **Bericht omleiden naar andere e-mailadressen**
       - **Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**
       - **Het bericht in quarantaine plaatsen**
       - **Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**
       - **Het bericht verwijderen voordat het wordt bezorgd**

     - **Als e-mail** wordt verzonden door een nagebootsd domein: Configureer een van de volgende acties voor berichten waarbij het domein van de afzender zich in een van de beveiligde domeinen die u hebt opgegeven in **Domeinen** toevoegen ter bescherming:

       - **Geen actie toepassen**
       - **Bericht omleiden naar andere e-mailadressen**
       - **Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**
       - **Het bericht in quarantaine plaatsen**
       - **Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**
       - **Het bericht verwijderen voordat het wordt bezorgd**

   - Klik **op veiligheidstips voor imitatie in-** en configureren een van de volgende instellingen:

     - **Tip voor imiteerde gebruikers tonen**
     - **Tip voor nagebootste domeinen tonen**
     - **Tip voor ongebruikelijke tekens tonen**

     De standaardwaarde voor alle tips is **Uitgeschakeld.** ![ ](../../media/scc-toggle-off.png) Als u een van deze in wilt schakelen, schuift u de schakelknop naar  [In-/uitschakelen.](../../media/scc-toggle-on.png)

     Klik op **Opslaan** wanneer u gereed bent.

   - **Postvakintelligentie:**

     - **Postvakintelligentie inschakelen?**: De standaardwaarde is **Ingeschakeld.** [](../../media/scc-toggle-on.png) Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.

     - **Postvakintelligentie inschakelen op basis van imitatiebeveiliging?**: Deze instelling is alleen beschikbaar als **Postvakintelligentie inschakelen is** **ingeschakeld.** Schakel deze instelling in om de actie op te geven die u moet ondernemen voor berichten voor imitatiedetecties van postvakinformatieresultaten.

       In **Als e-mail wordt** verzonden door een nagebootsde gebruiker, kunt u een van de volgende acties opgeven (dezelfde acties die beschikbaar zijn voor beveiligde gebruikers en beveiligde domeinen):

       - **Pas geen actie** toe: houd er rekening mee dat deze waarde hetzelfde resultaat heeft als het inschakelen van postvakinformatie inschakelen? maar postvakintelligentie op basis van  **imitatiebeveiliging inschakelen uitschakelen?**.
       - **Bericht omleiden naar andere e-mailadressen**
       - **Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**
       - **Het bericht in quarantaine plaatsen**
       - **Het bericht bezorgen en andere adressen toevoegen aan de BCC-regel**
       - **Het bericht verwijderen voordat het wordt bezorgd**

   - **Vertrouwde afzenders en domeinen toevoegen:** geef uitzonderingen op voor het beleid:

     - **Vertrouwde afzenders:**

       - Klik in het vak en blader door de lijst met gebruikers die u wilt selecteren.
       - Klik in het vak en begin te typen om de lijst te filteren en selecteer een gebruiker.
       - Als u een item wilt verwijderen, klikt **u op Pictogram** Verwijderen van de ![ ](../../media/scc-remove-icon.png) gebruiker.

     - **Vertrouwde domeinen:** Voer de domeinnaam in (bijvoorbeeld contoso.com), druk op Enter en herhaal indien nodig.

   - **Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.

     - U kunt in elke **sectie op Bewerken** klikken om terug te gaan naar de relevante pagina.
     - U kunt de volgende instellingen  rechtstreeks **op** deze pagina in- of uitschakelen:

       - **Beveiligde gebruikers**
       - **Beveiligde domeinen** \> **Domeinen opnemen die ik bezit**
       - **Beveiligde domeinen** \> **Beveiligde domeinen** (aangepaste domeinen)
       - **Postvakintelligentie**

   Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.

6. **Spoof:** Klik op **Bewerken** om spoofinformatie in of uit te schakelen, unauthenticated sender identification in Outlook in of uit te schakelen en de actie te configureren die van toepassing is op berichten van geblokkeerde vervalste afzenders. Zie Spoofinstellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie over deze instellingen.

   Houd er rekening mee dat deze instellingen ook beschikbaar zijn in anti-phishingbeleid in EOP.

   - **Filterinstellingen voor spoofing:** gebruik de instelling **Spoof intelligence inschakelen?** om spoofinformatie in of uit te schakelen. De standaardwaarde is **Aan** en we raden u aan deze aan te laten staan. Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.

     > [!NOTE]
     > U hoeft de bescherming tegen spoofing niet uit te schakelen als uw MX-record niet naar de Microsoft 365; u in plaats daarvan Verbeterde filtering voor verbindingslijnen inschakelen. Zie [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - **Instellingen voor niet-nautische afzenders:** U kunt de volgende instellingen configureren:
     - **Unauthenticated sender question mark (?)** symbol inschakelen? : Voeg een vraagteken toe aan de foto van de afzender in het  vak Van in Outlook als het bericht niet door SPF- of DKIM-controles wordt gecontroleerd en het bericht niet door DMARC of samengestelde verificatie [gaat.](email-validation-and-authentication.md#composite-authentication) De standaardwaarde is **Aan**. Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.
     - **Tag 'via' inschakelen?**: Voeg de via-tag (chris@contoso.com via fabrikam.com) toe als het e-mailadres in het vak Van verschilt van het domein in de DKIM-handtekening of het **MAIL FROM-adres.** De standaardwaarde is **Aan**. Als u deze wilt uitschakelen, schuift u de schakelknop naar **Uit-** ![ of ](../../media/scc-toggle-off.png) uitschakelen.

   - **Acties:** Geef de actie op voor berichten van geblokkeerde vervalste afzenders:

     **Als e-mail wordt verzonden door iemand die uw** domein niet mag vervalsen:

     - **Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden**
     - **Het bericht in quarantaine plaatsen**

   - **Uw instellingen controleren:** In plaats van op elke afzonderlijke stap te klikken, worden de instellingen weergegeven in een overzicht.

     - U kunt in elke **sectie op Bewerken** klikken om terug te gaan naar de relevante pagina.
     - U kunt de volgende instellingen  rechtstreeks **op** deze pagina in- of uitschakelen:
       - **Instellingen voor spooffilters**
       - **Instellingen voor niet-genauteerde afzender**
       - **Acties**

   Wanneer u klaar bent, klikt u op **Opslaan** op een pagina.

7. **Geavanceerde instellingen:** Klik op **Bewerken om** de geavanceerde phishingdrempels te configureren. Zie Advanced [phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   - **Geavanceerde phishingdrempels:** Selecteer een van de volgende waarden:

   - **1 - Standaard** (Dit is de standaardwaarde.)
   - **2 - Agressief**
   - **3 - Agressiever**
   - **4 - Meest agressief**

   - **Uw instellingen controleren:** Klik op **Bewerken om** terug te gaan naar de **pagina Geavanceerde phishingdrempels.**

   Wanneer u klaar bent, klikt u **op Opslaan** op beide pagina's.

8. Bekijk de instellingen op **de \<Name\> pagina** Uw beleid bewerken en klik vervolgens op **Sluiten.**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a>Gebruik het Beveiligings- & compliancecentrum om het standaard anti-phishingbeleid in Microsoft Defender voor Office 365

Het standaard anti-phishingbeleid in Microsoft Defender voor Office 365 heet Office365 AntiPhish Default en wordt niet weergegeven in de lijst met beleidsregels. Als u het standaard anti-phishingbeleid wilt wijzigen, gaat u als volgt te werk:

1. Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Klik op **de pagina Anti-phishing** op **Standaardbeleid.**

3. De **pagina Uw beleid bewerken Office365 AntiPhish Default** wordt weergegeven. De volgende secties zijn beschikbaar, die identieke instellingen bevatten voor wanneer u [een aangepast beleid wijzigt:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **Imitatie**
   - **Spoof**
   - **Geavanceerde instellingen**

   De volgende instellingen zijn niet beschikbaar wanneer u het standaardbeleid wijzigt:

   - U kunt  de sectie Beleidsinstelling en -waarden  zien, maar er is geen koppeling Bewerken, dus u kunt de instellingen niet wijzigen (beleidsnaam, beschrijving en op wie het beleid van toepassing is (dit geldt voor alle geadresseerden)).
   - U kunt het standaardbeleid niet verwijderen.
   - U kunt de prioriteit van het standaardbeleid niet wijzigen (dit wordt altijd als laatste toegepast).

4. Controleer op **de pagina Uw beleid bewerken Office365 AntiPhish Default** uw instellingen en klik vervolgens op **Sluiten.**

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Aangepaste anti-phishingbeleidsregels in- of uitschakelen in Microsoft Defender voor Office 365

1. Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Let op de waarde in de **kolom Status:**

   - Schuif de schakelknop naar  ![ Uit-schakelknop uit ](../../media/scc-toggle-off.png) om het beleid uit te schakelen.

   - Schuif de schakelknop naar  ![ Aan-aan om ](../../media/scc-toggle-on.png) het beleid in te schakelen.

U kunt het standaard anti-phishingbeleid niet uitschakelen.

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>De prioriteit instellen van aangepast anti-phishingbeleid in Microsoft Defender voor Office 365

Anti-phishingbeleid krijgt standaard een prioriteit die is gebaseerd op de volgorde waarin ze zijn gemaakt (nieuwere beleidsregels hebben een lagere prioriteit dan oudere beleidsregels). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Aangepaste anti-phishingbeleidsregels worden weergegeven in de volgorde waarin ze worden verwerkt (het eerste beleid heeft de **prioriteitswaarde** 0). Het standaard anti-phishingbeleid met de naam Office365 AntiPhish Default heeft de aangepaste prioriteitswaarde **Laag** en u kunt deze niet wijzigen.

 **Opmerking:** In het & compliancecentrum kunt u alleen de prioriteit van het anti-phishingbeleid wijzigen nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit overschrijven wanneer u de anti-phish-regel maakt (die van invloed kan zijn op de prioriteit van bestaande regels).

Als u de prioriteit van  een beleid wilt wijzigen, klikt u op Prioriteit verhogen  of Prioriteit verlagen **in** de eigenschappen van het beleid (u kunt het prioriteitsnummer niet rechtstreeks wijzigen in het Beveiligings- & Compliancecentrum). Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.

1. Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Selecteer het beleid dat u wilt wijzigen. Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.

3. Het **fly-out \<name\> Beleid** bewerken wordt weergegeven.

   - Het aangepaste anti-phishingbeleid met **prioriteitswaarde** **0** heeft alleen de **knop Prioriteit verlagen** beschikbaar.

   - Het aangepaste anti-phishingbeleid  met de laagste prioriteitswaarde (bijvoorbeeld **3)** heeft alleen de knop **Prioriteit verhogen** beschikbaar.

   - Als u drie of meer aangepaste anti-phishingbeleidsregels hebt, hebben  beleidsregels  tussen de waarden met de hoogste en laagste prioriteit zowel de knoppen Prioriteit verhogen als Prioriteit verlagen beschikbaar.

4. Klik **op Prioriteit verhogen of** Prioriteit verlagen **om** de waarde Prioriteit **te** wijzigen.

5. Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid in Microsoft Defender voor Office 365

1. Ga in het & compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Ga op een van de volgende stappen te werk:

   - Selecteer een aangepast anti-phishingbeleid dat u wilt weergeven. Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.

   - Klik **op Standaardbeleid** om het standaardbeleid voor anti-phishing te bekijken.

3. Het **fly-out \<name\>** Beleid bewerken wordt weergegeven, waar u de instellingen en waarden kunt bekijken.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Gebruik het Beveiligings- & compliancecentrum om anti-phishingbeleid in Microsoft Defender te verwijderen voor Office 365

1. Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**.

2. Selecteer het beleid dat u wilt verwijderen. Als deze optie al is geselecteerd, deselecteert u de selectie en selecteert u deze opnieuw.

3. Klik in **het \<name\> flyout** Beleid bewerken dat wordt weergegeven op Beleid verwijderen **en** klik vervolgens op **Ja** in het waarschuwingsdialoogvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Gebruik Exchange Online PowerShell om anti-phishingbeleid in Microsoft Defender te configureren voor Office 365

Zoals eerder beschreven, bestaat een antispambeleid uit een anti-phish-beleid en een anti-phish-regel.

In Exchange Online PowerShell is het verschil tussen anti-phish-beleid en anti-phish-regels duidelijk. U beheert anti-phish-beleid met behulp van **\* de cmdlets -AntiPhishPolicy** en u beheert anti-phish-regels met behulp van de **\* cmdlets -AntiPhishRule.**

- In PowerShell maakt u eerst het anti-phish-beleid en vervolgens maakt u de anti-phish-regel waarin het beleid wordt aangegeven waar de regel op van toepassing is.
- In PowerShell wijzigt u de instellingen in het anti-phish-beleid en de anti-phish-regel afzonderlijk.
- Wanneer u een anti-phish-beleid verwijdert uit PowerShell, wordt de bijbehorende anti-phish-regel niet automatisch verwijderd en omgekeerd.

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
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In dit voorbeeld wordt anti-phishbeleid met de naam Onderzoek quarantaine gemaakt met de volgende instellingen:

- Het beleid is ingeschakeld (we gebruiken de parameter _Ingeschakeld_ niet en de standaardwaarde is `$true` ).
- De beschrijving is: Het beleid van de onderzoeksafdeling.
- Hiermee wordt de beveiliging van organisatiedomeinen voor alle geaccepteerde domeinen en de bescherming van gerichte domeinen voor fabrikam.com.
- Hiermee geeft u Mai Fujito (mfujito@fabrikam.com) op als de gebruiker die u wilt beschermen tegen imitatie.
- Hiermee schakelt u postvakintelligentie in.
- Hiermee schakelt u de beveiliging van postvakintelligentie in en geeft u de quarantaineactie op.
- Hiermee schakelt u veiligheidstips in.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
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

Naast de volgende items zijn dezelfde instellingen beschikbaar wanneer u een anti-phish-beleid in PowerShell wijzigt als wanneer u het beleid maakt zoals beschreven in stap 1: PowerShell gebruiken om eerder in dit artikel een [anti-phish-beleid](#step-1-use-powershell-to-create-an-anti-phish-policy) te maken.

- De _schakelknop MakeDefault_ die het opgegeven beleid verandert in  het standaardbeleid (toegepast op iedereen, altijd Laagste prioriteit en u kunt het niet verwijderen) is alleen beschikbaar wanneer u een anti-phish-beleid wijzigt in PowerShell.

- U kunt de naam van een anti-phish-beleid niet wijzigen (de cmdlet **Set-AntiPhishPolicy** heeft geen _naamparameter)._ Wanneer u de naam van een anti-phishingbeleid wijzigt in het Beveiligings- & Compliancecentrum, wijzigt u alleen de naam van de anti-phish-regel.

Als u een anti-phish-beleid wilt wijzigen, gebruikt u de volgende syntaxis:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)voor gedetailleerde syntaxis- en parametergegevens.

### <a name="use-powershell-to-modify-anti-phish-rules"></a>PowerShell gebruiken om anti-phish-regels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een anti-phish-regel in PowerShell wijzigt, is de _parameter_ Ingeschakeld waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie als u bestaande anti-phish-regels wilt in- of uitschakelen.

Anders zijn er geen extra instellingen beschikbaar wanneer u een anti-phish-regel in PowerShell wijzigt. Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals beschreven in stap 2: PowerShell gebruiken om eerder in dit artikel een [anti-phish-regelsectie](#step-2-use-powershell-to-create-an-anti-phish-rule) te maken.

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

Als u wilt controleren of u anti-phishingbeleid hebt geconfigureerd in Microsoft Defender voor Office 365, gaat u als volgt te werk:

- Ga in het & Compliancecentrum naar **Threat management** \> **Policy** \> **Anti-phishing**. Controleer de lijst met beleidsregels, de **statuswaarden** en de **prioriteitswaarden.** Ga als volgt te werk om meer details weer te geven:

  - Selecteer het beleid in de lijst en bekijk de details in de flyout.
  - Klik **op Standaardbeleid** en bekijk de details in de flyout.

- Vervang Exchange Online PowerShell door de naam van het beleid of de regel en voer de volgende opdracht uit \<Name\> en controleer de instellingen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```