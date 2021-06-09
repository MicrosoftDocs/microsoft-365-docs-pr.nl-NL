---
title: Spamfilterbeleid configureren
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Beheerders kunnen het antispambeleid in Exchange Online Protection (EOP) bekijken, maken, wijzigen en verwijderen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2214baa1c205d4e0f634c5a07f4d55522d2ad6b1
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822019"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Antispambeleid configureren in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of standalone EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, zijn binnenkomende e-mailberichten automatisch tegen spam beschermd door EOP. EOP gebruikt antispambeleid (ook wel bekend als spamfilterbeleid of inhoudsfilterbeleid) als onderdeel van de algehele bescherming van uw bedrijf tegen spam. Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.

Beheerders kunnen het standaardbeleid bekijken, bewerken en configureren (maar niet verwijderen). Voor grotere nauwkeurigheid kunt u ook aangepast antispambeleid maken dat wordt toegepast op specifieke gebruikers, groepen of domeinen binnen uw bedrijf. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U kunt antispambeleid configureren in het Microsoft 365-beveiligingscentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

De basiselementen van antispambeleid zijn: 

- **Het spamfilterbeleid**: omschrijft de acties voor spamfilterbeoordelingen en de meldingsopties.
- **De spamfilterregel**: omschrijft de prioriteits- en geadresseerdenfilters (waarop het beleid van toepassing is) voor spamfilterbeleid.

Het verschil tussen deze twee elementen is niet overduidelijk wanneer u antispambeleid beheert in het beveiligingscentrum:

- Wanneer u antispambeleid maakt, maakt u in feite tegelijkertijd een spamfilterregel en het bijbehorende spamfilterbeleid met dezelfde naam voor beide.
- Wanneer u antispambeleid wijzigt, wordt de spamfilterregel gewijzigd door instellingen met betrekking tot de naam, prioriteit, in- of uitgeschakeld en geadresseerdenfilters. Alle andere instellingen wijzigen het bijbehorende spamfilterbeleid.
- Wanneer u antispambeleid verwijdert, worden de spamfilterregel en het bijbehorende spamfilterbeleid verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie [Exchange Online PowerShell of standalone EOP PowerShell gebruiken om antispambeleid te configureren](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) later in dit artikel voor meer informatie.

Elk bedrijf heeft een ingebouwd antispambeleid met de naam Standaard met de volgende eigenschappen:

- Het beleid wordt toegepast op alle geadresseerden in het bedrijf, ook al is er geen spamfilterregel (geadresseerdenregels) gekoppeld aan het beleid.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Om de effectiviteit van spamfilters te verhogen, kunt u aangepast antispambeleid maken met strengere instellingen dat wordt toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligingscentrum in <https://security.microsoft.com>. Gebruik <https://security.microsoft.com/antispam> om direct naar de pagina **Antispambeleid** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als je antispambeleid wilt toevoegen, wijzigen of verwijderen, moet je lid zijn van de functiegroep **Organisatiebeheer** of **Beveiligingsbeheer**.
  - Voor alleen-lezentoegang tot het antispambeleid moet je lid zijn van de functiegroep **Global Reader** of **Beveiligingslezer**.

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.

- Zie [Instellingen voor antispambeleid in EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)voor de aanbevolen instellingen voor antispambeleid.

## <a name="use-the-security-center-to-create-anti-spam-policies"></a>Het beveiligingscentrum gebruiken om antispambeleid te maken

Wanneer u antispambeleid maakt in het beveiligingscentrum worden tegelijkertijd een spamfilterregel en het bijbehorende spamfilterbeleid gemaakt met dezelfde naam voor beide.

1. Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispambeleid** achtereenvolgens op ![Pictogram maken](../../media/m365-cc-sc-create-icon.png), **Beleid maken** en selecteer in de vervolgkeuzelijst de optie **Binnenkomend**.

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

5. Configureer de volgende instellingen op de pagina **Drempelwaarde bulkmail en spameigenschappen**:

   - **Drempelwaarde bulkmail**: hiermee wordt het bulkklachtniveau (BCL) van een bericht aangegeven dat de gespecificeerde actie activeert voor de **Bulk**-spamfilterbeoordeling die u op de volgende pagina configureert (groter dan de opgegeven waarde, niet groter dan of gelijk aan). Een hogere waarde geeft aan dat het bericht minder wenselijk is (grotere kans dat het bericht spam is). De standaardwaarde is 7. Zie [Bulkklachtniveau (BCL) in EOP](bulk-complaint-level-values.md) en [Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) voor meer informatie.

     Standaard is de enige PowerShell-instelling _MarkAsSpamBulkMail_ `On` in antispambeleid. Deze instelling is van grote invloed op de resultaten van een **Bulk**-filterbeoordeling:

     - **_MarkAsSpamBulkMail_ is ingeschakeld**: een BCL dat groter is dan de drempelwaarde wordt geconverteerd naar een SCL 6, wat overeenkomt met een filterbeoordeling van **Spam** en de actie voor de **Bulk**-filterbeoordeling wordt toegepast op het bericht.
     - **_MarkAsSpamBulkMail_ is uitgeschakeld**: het bericht krijgt het stempel BCL, maar er wordt _geen actie_ uitgevoerd voor een **Bulk**-filterbeoordeling. Het gevolg is dat de BCL-drempelwaarde en de actie voor de **Bulk**-filterbeoordeling niet relevant zijn.

   - **Spamscore verhogen**, **Markeren als spam**<sup>\*</sup> en **Testmodus**: bevat de instellingen voor de geavanceerde spamfilter (ASF) die standaard zijn uitgeschakeld. ASF-instellingen worden afgeschaft en hun functionaliteit wordt opgenomen in andere onderdelen van de filterstack. Het is raadzaam dat u al deze ASF-instellingen uitgeschakeld laat in uw antispambeleid.

     Zie [Geavanceerde instellingen voor spamfilters in EOP](advanced-spam-filtering-asf-options.md) voor meer informatie over deze instellingen.

      <sup>\*</sup> **Bevat specifieke talen** en **uit deze landen** maken geen deel uit van ASF-instellingen.

   - **Bevat specifieke talen**: klik in het vak en selecteer **Aan** of **Uit** in de vervolgkeuzelijst. Als u deze inschakelt, wordt een vak weergegeven. Begin de naam van een taal te typen in het vak. Er wordt een gefilterde lijst met ondersteunde talen weergegeven. Wanneer u de gezochte taal vindt, selecteert u die. Herhaal deze stap zo vaak als nodig is. Als u een bestaande waarde wilt verwijderen, klikt u op ![Pictogram verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

   - **Uit deze landen** _: klik in het vak en selecteer_ *Aan** of **Uit** in de vervolgkeuzelijst. Als u deze inschakelt, wordt een vak weergegeven. Begin de naam van een land te typen in het vak. Er wordt een gefilterde lijst met ondersteunde landen weergegeven. Selecteer het land of de regio waarnaar u zocht als het is gevonden. Herhaal deze stap zo vaak als nodig is. Als u een bestaande waarde wilt verwijderen, klikt u op ![Pictogram verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

   Wanneer u gereed bent, klikt u op **Volgende**.

6. Configureer de volgende instellingen op de pagina **Acties** die wordt weergegeven:

   - **Berichtacties**: selecteer of bekijk de actie die moet worden uitgevoerd op berichten op basis van de volgende spamfilterbeoordelingen:
     - **Spam**
     - **Hoogstwaarschijnlijk spam**
     - **phishing**
     - **Phishing met hoge waarschijnlijkheid**
     - **Bulk**

     De beschikbare acties voor spamfilterbeoordelingen worden beschreven in de volgende tabel.

     - Een vinkje ( ![vinkje](../../media/checkmark.png)) geeft aan dat de actie beschikbaar is (niet alle acties zijn beschikbaar voor alle beoordelingen).
     - Een asterisk (<sup>\*</sup>) na het vinkje geeft de standaardactie aan voor de spamfilterbeoordeling. 

     <br>

     ****

     |Actie|Spam|Hoog<br>betrouwbaarheid<br>spam|Phishing|Hoog<br>betrouwbaarheid<br>phishing|Bulk|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Bericht verplaatsen naar de map Ongewenste e-mail**: het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail.<sup>1</sup>|![Vinkje](../../media/checkmark.png)<sup>\*</sup>|![Vinkje](../../media/checkmark.png)<sup>\*</sup>|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)<sup>\*</sup>|
     |**X-kop toevoegen**: hiermee wordt een X-kop toegevoegd aan de berichtkop en het bericht bezorgd in het postvak. <p> U voert de veldnaam (niet de waarde) van de X-kop later in het vak **Deze X-koptekst toevoegen** in.  <p> Bij de beoordelingen **Spam** en **Hoogstwaarschijnlijk spam** wordt het bericht verplaatst nar de map Ongewenste e-mail.<sup>1,2</sup>|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)||![Vinkje](../../media/checkmark.png)<sup>\*</sup>|
     |**Onderwerpregel vooraan uitbreiden met tekst**: hiermee wordt tekst toegevoegd aan het begin van de onderwerpregel van het bericht. Het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail.<sup>1,2</sup> <p> U voert de tekst later in het vak **Voeg deze tekst toe vooraan de onderwerpregel** in.|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)||![Vinkje](../../media/checkmark.png)|
     |**Bericht naar e-mailadres omleiden**: hiermee wordt het bericht omgeleid naar andere geadresseerden in plaats van de beoogde geadresseerde. <p> U geeft de geadresseerden later op in het vak **Omleiden naar dit e-mailadres**.|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
     |**Bericht verwijderen**: hiermee wordt het volledige bericht verwijderd, inclusief alle bijlagen.|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)||![Vinkje](../../media/checkmark.png)|
     |**Bericht in quarantaine**: hiermee wordt het bericht in quarantaine geplaatst in plaats van verzonden naar de beoogde geadresseerden. <p> U geeft later in het vak **Quarantaine** aan hoelang het bericht in quarantaine moet blijven.|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)<sup>\*</sup>|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
     |**Geen actie**|||||![Vinkje](../../media/checkmark.png)|
     |

     > <sup>1</sup> In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel Ongewenste e-mail is ingeschakeld voor het postvak (standaard is die regel ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.
     >
     > In hybride omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie [EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](/exchange/standalone-eop/configure-eop-spam-protection-hybrid) voor meer informatie. 
     >
     > <sup>2</sup> U kunt deze waarde gebruiken als voorwaarde in e-mailstroomregels om het bericht te filteren of om te leiden.

   - **Spam in quarantaine plaatsen voor zoveel dagen**: geeft aan hoe lang het bericht in quarantaine moet worden gehouden als u de actie **Bericht in quarantaine plaatsen** hebt geselecteerd voor een spamfilterbeoordeling. Na het verlopen van de periode wordt het bericht verwijderd. De standaardwaarde is 30 dagen. Een geldige waarde ligt tussen de 1 en 30 dagen. Zie de volgende artikelen voor meer informatie over quarantaine:

     - [Berichten in quarantaine in EOP](quarantine-email-messages.md)
     - [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md)
     - [Berichten in quarantaine zoeken en vrijgeven als gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Deze X-koptekst toevoegen**: dit vak is alleen vereist en beschikbaar als u de actie **X-kop toevoegen** hebt geselecteerd voor een spamfilterbeoordeling. De waarde die u opgeeft, is de naam van het *kopveld* dat wordt toegevoegd aan de berichtkop. De kopveld *waarde* is altijd `This message appears to be spam`.

     De maximumlengte is 255 tekens en de waarde kan geen spaties of dubbele punten (:) bevatten.

     Als u bijvoorbeeld de waarde `X-This-is-my-custom-header` opgeeft, wordt de X-kop `X-This-is-my-custom-header: This message appears to be spam.` toegevoegd aan het bericht.

     Als u een waarde opgeeft die spaties of dubbele punten (:) bevat, wordt de ingevoerde waarde genegeerd en wordt de standaard-X-kop (`X-This-Is-Spam: This message appears to be spam.`) aan het bericht toegevoegd.

   - **Onderwerpregel vooraan uitbreiden met deze tekst**: dit vak is alleen vereist en beschikbaar als u de actie **Onderwerpregel vooraan uitbreiden met tekst** hebt geselecteerd voor een spamfilterbeoordeling. Voer de tekst in die moet worden toegevoegd aan het begin van de onderwerpregel van het bericht.

   - **Bericht naar dit e-mailadres omleiden**: dit vak is alleen vereist en beschikbaar als u de actie **Bericht naar e-mailadres omleiden** hebt geselecteerd voor een spamfilterbeoordeling. Voer het e-mailadres in waarnaar u het bericht wilt verzenden. U kunt meerdere waarden opgeven, gescheiden door puntkomma’s (;).

   - **Veiligheidstips inschakelen**: standaard staan veiligheidstips ingeschakeld, maar u kunt ze uitschakelen door het selectievakje uit te schakelen. Zie [Veiligheidstips in e-mailberichten](safety-tips-in-office-365.md) voor meer informatie over veiligheidstips.

   - **Zero-hour auto purge (ZAP) inschakelen**: ZAP detecteert en voert actie uit op berichten die al zijn afgeleverd aan Exchange Online-postvakken. Zie [Zero-hour auto purge - beveiliging tegen ongewenste e-mail en malware](zero-hour-auto-purge.md) voor meer informatie.

     ZAP is standaard ingeschakeld. Wanneer ZAP is ingeschakeld, zijn de volgende instellingen beschikbaar:

     - **ZAP inschakelen voor phishingberichten**: ZAP is standaard ingeschakeld voor phishingdetectie, maar u kunt het uitschakelen door het selectievakje uit te schakelen.
     - **ZAP inschakelen voor spamberichten**: ZAP is standaard ingeschakeld voor spamdetectie, maar u kunt het uitschakelen door het selectievakje uit te schakelen.

   - **Spammeldingen voor eindgebruikers inschakelen**: zie de sectie [Spammeldingen voor eindgebruikers configureren](#configure-end-user-spam-notifications) verderop in dit onderwerp voor meer informatie.

   Wanneer u gereed bent, klikt u op **Volgende**.

7. Op de flyout **Lijst toestaan en blokkeren** die wordt weergegeven, kunt u op basis van e-mailadres of e-maildomein afzenders van berichten configureren die de spamfilters mogen overslaan.

   In de sectie **Toegestaan** kunt u toegestane afzenders en toegestane domeinen configureren. In de sectie **Geblokkeerd** kunt u geblokkeerde afzenders en geblokkeerde domeinen toevoegen.

   > [!IMPORTANT]
   >
   > Denk goed na voordat u domeinen toevoegt aan de lijst met toegestane domeinen. Zie [Lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md) voor meer informatie.
   >
   > • Voeg nooit uw eigen [geaccepteerde domeinen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) of algemene domeinen (bijv.: microsoft.com of office.com) toe aan de lijst met toegestane domeinen. Als het is toegestaan dat deze domeinen spamfilters omzeilen, kunnen kwaadwillende gebruikers eenvoudig e-mails naar uw organisatie verzenden.
   >
   > Het is niet gevaarlijk handmatig domeinen te blokkeren door ze aan de lijst met geblokkeerde domeinen toe te voegen, maar het kan de werkbelasting vergroten. Zie [Lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md) voor meer informatie.
   >
   > Er zijn momenten waarop de filters het bericht missen, u het niet eens bent met het filteroordeel of het even duurt voor de systemen helemaal bijgewerkt zijn. In deze gevallen zijn de lijsten Toegestaan en Geblokkeerd beschikbaar om de huidige filterbeoordelingen te overschrijven. Maar u dient dezer lijsten spaarzaam en tijdelijk te gebruiken, omdat lange lijsten onbeheerbaar kunnen worden en de filterstack moet doen waarvoor die is ingesteld. Als u echter een toegestaan domein voor een langere periode behoudt, moet u dat de afzender laten weten om zeker te weten dat het domein is geverifieerd en ingesteld op DMARC als dat niet zo is.

   De stappen voor het toevoegen van vermeldingen aan een van de lijsten zijn hetzelfde:

   1. Klik op de koppeling voor de lijst die u wilt configureren:
      - **Toegestane** \> **afzenders**: Klik op **(nn) afzender(s) beheren**.
      - **Toegestane** \> **domeinen**: Klik op **Domeinen toestaan**.
      - **Geblokkeerde** \> **afzenders**: Klik op **(nn) afzender(s) beheren**.
      - **Geblokkeerde** \> **domeinen**: Klik op **Domeinen blokkeren**.

   2. Doe in de flyout die wordt weergegeven, het volgende:
      1. Klik op ![Pictogram maken](../../media/m365-cc-sc-create-icon.png) **Afzenders toevoegen** of **Domeinen toevoegen**.
      2. Typ in de flyout **Afzenders toevoegen** of **Domeinen toevoegen** die wordt weergegeven, het e-mailadres van de afzender in het vak **Afzender** of het domein in het vak **Domein**. Terwijl u typt, wordt de waarde onder het vak weergegeven. Wanneer u klaar bent met het typen van het e-mailadres of domein, selecteert u de waarde onder het vak.
      3. Herhaal deze stap zo vaak als nodig is. Als u een bestaande waarde wilt verwijderen, klikt u op verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-remove-selection-icon.png) naast de waarde.

      Wanneer u klaar bent, klikt u op **Afzenders toevoegen** of **Domeinen toevoegen**.

      In de hoofdflyout worden de afzenders of domeinen die u hebt toegevoegd, weergegeven op de pagina. Ga als volgt te werk om een vermelding van deze pagina te verwijderen:

      1. Selecteer een of meer vermeldingen in de lijst. U kunt ook het **zoekvak** gebruiken om waarden te vinden in de lijst.
      2. Nadat u ten minste één vermelding hebt geselecteerd, wordt het pictogram verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-delete-icon.png) weergegeven.
      3. Klik op het pictogram verwijderen ![Pictogram Verwijderen](../../media/m365-cc-sc-delete-icon.png) om de geselecteerde vermeldingen te verwijderen.

      Klik op **Gereed** als u klaar bent.

      Klik op de pagina **Lijst met toegestaan en geblokkeerd** op **Volgende** wanneer u wordt gevraagd om door te gaan.

8. Controleer uw instellingen op de pagina **Controleren** die wordt weergegeven. U kunt in elke sectie **Bewerken** selecteren om de instellingen in de sectie te wijzigen. U kunt ook op **Terug** klikken of de specifieke pagina in de wizard selecteren.

   Klik op **Maken** wanneer u gereed bent.

9. Klik op de bevestigingspagina die wordt weergegeven op **Gereed**.

## <a name="use-the-security-center-to-view-anti-spam-policies"></a>Het beveiligingscentrum gebruiken om antispambeleid te bekijken

1. Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Zoek op de pagina **Antispambeleid** een van de volgende waarden:
   - De waarde **Type** is **Aangepast antispambeleid**
   - De waarde **Naam** is **Antispambeleid voor binnenkomende spam (standaard)**

   De volgende eigenschappen worden weergegeven in de lijst met antispambeleidsregels:

   - **Naam**
   - **Status**
   - **Prioriteit**
   - **Type**

3. Wanneer u een antispambeleid selecteert door op de naam te klikken, worden de beleidsinstellingen weergegeven in een flyout.

## <a name="use-the-security-center-to-modify-anti-spam-policies"></a>Het beveiligingscentrum gebruiken om antispambeleid aan te passen

1. Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Selecteer op de pagina **Antispambeleidsregels** een antispambeleid in de lijst door op de naam te klikken:
   - Aangepast beleid dat u hebt gemaakt, waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is.
   - Het standaardbeleid met de naam **Antispambeleid voor binnenkomende spam (standaard)**.

3. U kunt in de flyout met beleidsdetails in elke sectie de optie **Bewerken** selecteren om de instellingen in de sectie te wijzigen. Zie de vorige sectie in dit artikel over [Het beveiligingscentrum gebruiken om antispambeleid te maken](#use-the-security-center-to-create-anti-spam-policies) voor meer informatie over de instellingen.

   Voor het standaardantispambeleid is de sectie **Toegepast op** niet beschikbaar (het beleid is op iedereen van toepassing) en u kunt de naam van het beleid niet wijzigen.

Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.

### <a name="enable-or-disable-anti-spam-policies"></a>Antispambeleid in- of uitschakelen

U kunt het standaardantispambeleid niet uitschakelen.

1. Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Selecteer op de pagina **Antispambeleid** een beleid met de **Waarde type** van **Aangepast antispambeleid** uit de lijst door op de naam de klikken.

3. Boven aan de flyout met beleidsdetails die wordt weergegeven, ziet u een van de volgende waarden:
   - **Beleid uitgeschakeld**: als u het beleid wilt inschakelen, klikt u op ![Pictogram inschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Inschakelen** .
   - **Beleid ingeschakeld**: als u het beleid wilt uitschakelen, klikt u op ![Pictogram uitschakelen](../../media/m365-cc-sc-turn-on-off-icon.png) **Uitschakelen**.

4. Klik in het bevestigingsvenster dat wordt weergegeven op **Inschakelen** of **Uitschakelen**.

5. Klik in de flyout met beleidsdetails op **Sluiten**.

Op de hoofdbeleidspagina wordt de waarde **Status** van het beleid weergegeven als **Ingeschakeld** of **Uitgeschakeld**.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>De prioriteit instellen voor aangepast antispambeleid

Standaard krijgt antispambeleid een prioriteit op basis van de volgorde waarin het is gemaakt (nieuwer beleid heeft een hogere prioriteit dan ouder beleid). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Als u de prioriteit van een beleid wilt wijzigen, klikt u op **Prioriteit verhogen** of **Prioriteit verlagen** in de eigenschappen van het beleid (u kunt het **Prioriteitsnummer** niet rechtstreeks wijzigen in het beveiligingscentrum). Het wijzigen van de prioriteit van een beleid is alleen zinvol als u meerdere beleidsregels hebt.

 **Opmerkingen**:

- In het beveiligingscentrum kunt u alleen de prioriteit wijzigen van het antispambeleid nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit vervangen wanneer u de spamfilterbeleidsregel maakt (die kan de prioriteit van bestaande regels beïnvloeden).
- Antispambeleid wordt verwerkt in de volgorde waarin het wordt weergegeven (het eerste beleid heeft de **Prioriteitswaarde** 0). Het standaardantispambeleid heeft de prioriteitswaarde **Laagste** en dat kunt u niet wijzigen.

1. Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Selecteer op de pagina **Antispambeleid** een beleid met de **Waarde type** van **Aangepast antispambeleid** uit de lijst door op de naam de klikken.

3. Boven aan de flyout met beleidsgegevens die wordt weergegeven, ziet u **Prioriteit verhogen** of **Prioriteit verlagen** op basis van de huidige prioriteitswaarde en het aantal aangepaste beleidsregels:
   - Voor het antispambeleid met de **Prioriteitswaarde** **0** is alleen de optie **Prioriteit verlagen** beschikbaar.
   - Voor het antispambeleid met de laagste **Prioriteitswaarde** (bijvoorbeeld **3**) is alleen de optie **Prioriteit verhogen** beschikbaar.
   - Als u drie of meer antispambeleidsregels hebt, zijn bij beleidsregels tussen de hoogste en laagste prioriteitswaarden zowel de optie **Prioriteit verhogen** als **Prioriteit verlagen** beschikbaar.

   Klik op het ![pictogram Prioriteit verhogen](../../media/m365-cc-sc-increase-icon.png) **Prioriteit verhogen** of ![Pictogram Prioriteit verlagen](../../media/m365-cc-sc-decrease-icon.png) **Prioriteit verlagen** om de **Prioriteitswaarde** te wijzigen.

4. Wanneer u klaar bent, klikt u in de flyout met beleidsdetails op **Sluiten**.

### <a name="configure-end-user-spam-notifications"></a>Spammeldingen voor eindgebruikers configureren

Wanneer in een spamfilterbeoordeling een bericht in quarantaine wordt geplaatst, kunt u spammeldingen voor eindgebruikers configureren om geadresseerden te laten weten wat er is gebeurd met berichten die naar hen zijn verzonden. Zie [Spammeldingen voor eindgebruikers in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor meer informatie over deze meldingen.

1. Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Selecteer op de pagina **Antispambeleidsregels** een antispambeleid in de lijst door op de naam te klikken:
   - Aangepast beleid dat u hebt gemaakt, waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is.
   - Het standaardbeleid met de naam **Antispambeleid voor binnenkomende spam (standaard)**.

3. Klik in de flyout met beleidsgegevens die wordt weergegeven op **Bewerken** in de sectie **Acties**. Configureer de volgende instellingen op de flyout **Acties** die wordt weergegeven:

   - **Spammeldingen voor eindgebruikers inschakelen**: selecteer het selectievakje om meldingen in te schakelen of deselecteer het selectievakje om meldingen uit te schakelen. Wanneer u het selectievakje selecteert, worden de volgende aanvullende instellingen weergegeven:

     - **Iedere (dagen) spammeldingen voor eindgebruikers verzenden**: selecteer hoe vaak meldingen worden verzonden. De standaardwaarde is 3 dagen. U kunt 1 tot 15 dagen opgeven.

       Er zijn drie cycli van spammeldingen voor eindgebruikers binnen een periode van 24 uur die beginnen op de volgende tijden: 01:00 UTC, 08:00 UTC en 16:00 UTC.

       > [!NOTE]
       > Als we tijdens een vorige cyclus een melding hebben gemist, wordt in de volgende cyclus de melding gepusht. Dit geeft mogelijk de indruk van meerdere meldingen op dezelfde dag.

     - **Taal**: klik op de vervolgkeuzelijst en selecteer een beschikbare taal in de lijst. De standaardwaarde is **Standaard**, dat wil zeggen Engels.

   Klik op **Opslaan** wanneer u gereed bent.

4. Klik in de flyout met beleidsdetails weer op **Sluiten**.

## <a name="use-the-security-center-to-remove-custom-anti-spam-policies"></a>Het beveiligingscentrum gebruiken om aangepast antispambeleid te verwijderen

Wanneer u het beveiligingscentrum gebruikt om aangepast antispambeleid te verwijderen, worden de spamfilterregel en het bijbehorende spamfilterbeleid beide verwijderd. U kunt het standaardantispambeleid niet verwijderen.

1. Ga in het beveiligingscentrum naar **E-mail en samenwerking** \> **Beleid en regels** \> **Bedreigingsbeleid** \> sectie **Beleid** \> **Antispam**.

2. Selecteer op de pagina **Antispambeleid** een beleid met de **Waarde type** van **Aangepast antispambeleid** uit de lijst door op de naam de klikken. Klik boven aan de flyout met beleidsdetails die wordt weergegeven, op het ![pictogram Meer acties](../../media/m365-cc-sc-more-actions-icon.png) **Meer acties** \> ![Pictogram Beleid verwijderen](../../media/m365-cc-sc-delete-icon.png) **Beleid verwijderen**.

3. Klik in het bevestigingsvenster dat wordt weergegeven op **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Exchange Online PowerShell of standalone EOP PowerShell gebruiken om antispambeleid te configureren

Zoals eerder beschreven, bestaat een antispambeleid uit een spamfilterbeleid en een spamfilterregel.

In Exchange Online PowerShell of standalone EOP PowerShell is het verschil tussen spamfilterbeleid en spamfilterregels duidelijk. U beheert spamfilterbeleid door de cmdlets **\*-HostedContentFilterPolicy** te gebruiken en u beheert spamfilterregels door de cmdlets **\*-HostedContentFilterRule** te gebruiken. 

- In PowerShell maakt u eerst het spamfilterbeleid en vervolgens maakt u de spamfilterregel die het beleid identificeert waarop de regel van toepassing is.
- In PowerShell wijzigt u de instellingen in het spamfilterbeleid en de spamfilterregel afzonderlijk.
- Wanneer u spamfilterbeleid verwijdert uit PowerShell, wordt de bijbehorende spamfilterregel niet automatisch verwijderd en omgekeerd.

De volgende antispambeleidsinstellingen zijn alleen beschikbaar in PowerShell:

- De parameter _MarkAsSpamBulkMail_, die standaard `On` is. De gevolgen van deze instelling zijn eerder in dit artikel uitgelegd in de sectie [Het beveiligingscentrum gebruiken om antispambeleid te maken](#use-the-security-center-to-create-anti-spam-policies).

- De volgende instellingen voor quarantainemeldingen voor eindgebruikers:
  - De parameter _DownloadLink_ toont of verbergt de koppeling naar het rapportagehulpmiddel voor ongewenste e-mail voor Outlook.
  - De parameter _EndUserSpamNotificationCustomSubject_ die u kunt gebruiken om de onderwerpregel van de melding aan te passen.

### <a name="use-powershell-to-create-anti-spam-policies"></a>PowerShell gebruiken om antispambeleid te maken

Antispambeleid maken in PowerShell bestaat uit twee stappen:

1. Het spamfilterbeleid maken.
2. De spamfilterbeleidsregel maken die het spamfilterbeleid opgeeft waarop de regel van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe spamfilterbeleidsregel maken en een bestaand, niet-gekoppeld spamfilterbeleid eraan toewijzen. Een spamfilterbeleidsregel kan niet worden gekoppeld aan meer dan één spamfilterbeleid.
- U kunt de volgende instellingen voor nieuw spamfilterbeleid configureren in PowerShell die niet beschikbaar zijn in het beveiligingscentrum tot nadat u het beleid hebt gemaakt:
  - Schakel het nieuwe beleid uit (_Ingeschakeld_ `$false` in het cmdlet **New-HostedContentFilterRule**).
  - Stel de prioriteit van het beleid in tijdens het maken (_Prioriteit_ _\<Number\>_) in de cmdlet **New-HostedContentFilterRule**).

- Nieuw spamfilterbeleid dat u maakt in PowerShell is niet zichtbaar in het beveiligingscentrum totdat u het beleid toewijst aan een spamfilterregel.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Stap 1: PowerShell gebruiken om spamfilterbeleid te maken

Gebruik de volgende syntaxis om spamfilterbeleid te maken:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

Dit voorbeeld maakt spamfilterbeleid met de naam Contoso Executives met de volgende instellingen:

- Quarantainemeldingen wanneer de spamfilterbeoordeling Spam of Hoogstwaarschijnlijk spam is.
- BCL 7, 8 of 9 activeert de actie voor een bulk-e-mail-spamfilterbeoordeling.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

Zie [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

#### <a name="step-2-use-powershell-to-create-a-spam-filter-rule"></a>Stap 2: PowerShell gebruiken om een spamfilterregel te maken

Gebruik de volgende syntaxis om een spamfilterregel te maken:

```PowerShell
New-HostedContentFilterRule -Name "<RuleName>" -HostedContentFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

Dit voorbeeld maakt een nieuwe spamfilterregel met de naam Contoso Executives met de volgende instellingen:

- Het spamfilterbeleid met de naam Contoso Executives wordt gekoppeld aan de regel.
- De regel is van toepassing op leden van de groep met de naam Contoso Executives Group.

```PowerShell
New-HostedContentFilterRule -Name "Contoso Executives" -HostedContentFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Zie [New-HostedContentFilterRule](/powershell/module/exchange/new-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-spam-filter-policies"></a>PowerShell gebruiken om spamfilterbeleid te bekijken

Voer de volgende opdracht uit om een overzicht van alle spamfilterbeleid weer te geven:

```PowerShell
Get-HostedContentFilterPolicy
```

Gebruik deze syntaxis voor gedetailleerde informatie over specifiek spamfilterbeleid:

```PowerShell
Get-HostedContentFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In dit voorbeeld worden alle eigenschapswaarden weergegeven voor het spamfilterbeleid met de naam Executives.

```PowerShell
Get-HostedContentFilterPolicy -Identity "Executives" | Format-List
```

Zie [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-view-spam-filter-rules"></a>PowerShell gebruiken om spamfilterregels te bekijken

Gebruik de volgende syntaxis om bestaande spamfilterregels te bekijken:

```PowerShell
Get-HostedContentFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Voer de volgende opdracht uit om een overzicht van alle spamfilterregels weer te geven:

```PowerShell
Get-HostedContentFilterRule
```

Voer de volgende opdrachten uit om de lijst te filteren op ingeschakelde en uitgeschakelde regels:

```PowerShell
Get-HostedContentFilterRule -State Disabled
```

```PowerShell
Get-HostedContentFilterRule -State Enabled
```

Gebruik deze syntaxis voor gedetailleerde informatie over een specifieke spamfilterregel:

```PowerShell
Get-HostedContentFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In dit voorbeeld worden alle eigenschapswaarden weergegeven voor het spamfilterregel met de naam Contoso Executives.

```PowerShell
Get-HostedContentFilterRule -Identity "Contoso Executives" | Format-List
```

Zie [Get-HostedContentFilterRule](/powershell/module/exchange/get-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-spam-filter-policies"></a>PowerShell gebruiken om spamfilterbeleid te wijzigen

Voor het wijzigen van spamfilterbeleid in PowerShell zijn, behalve voor de volgende items, dezelfde instellingen beschikbaar als bij het maken van het beleid zoals eerder in dit artikel beschreven in de sectie [Stap 1: PowerShell gebruiken om spamfilterbeleid te maken](#step-1-use-powershell-to-create-a-spam-filter-policy).

- De schakeloptie _MakeDefault_ die het specifieke beleid wijzigt in het standaardbeleid (toegepast op iedereen, altijd **Laagste** prioriteit en kan niet worden verwijderd) is alleen beschikbaar wanneer u spamfilterbeleid wijzigt in PowerShell.
- U kunt de naam van het spamfilterbeleid niet wijzigen (het cmdlet **Set-HostedContentFilterPolicy** heeft geen parameter _Naam_). Wanneer u de naam van antispambeleid in het beveiligingscentrum wijzigt, wijzigt u alleen de naam van de spamfilter _regel_.

Gebruik de volgende syntaxis om spamfilterbeleid te wijzigen:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-spam-filter-rules"></a>PowerShell gebruiken om spamfilterregels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een spamfilterregel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie om bestaande spamfilterregels in of uit te schakelen.

Er zijn geen extra instellingen beschikbaar wanneer u een spamfilterregel wijzigt in PowerShell. Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals eerder in dit artikel beschreven in de sectie [Stap 2: PowerShell gebruiken om een spamfilterregel te maken](#step-2-use-powershell-to-create-a-spam-filter-rule).

Gebruik de volgende syntaxis om een spamfilterregel te wijzigen:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

In dit voorbeeld wordt de naam van de bestaande spamfilterregel gewijzigd naar `{Fabrikam Spam Filter}`.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Zie [Set-HostedContentFilterRule](/powershell/module/exchange/set-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-enable-or-disable-spam-filter-rules"></a>PowerShell gebruiken om spamfilterregels in of uit te schakelen

Het in- of uitschakelen van een spamfilterregel in PowerShell, schakelt het hele antispambeleid in of uit (de spamfilterregel en het bijbehorende spamfilterbeleid). U kunt het standaardbeleid niet in- of uitschakelen (dit wordt altijd toegepast op alle geadresseerden).

Gebruik de volgende syntaxis om een spamfilterregel in PowerShell in of uit te schakelen:

```PowerShell
<Enable-HostedContentFilterRule | Disable-HostedContentFilterRule> -Identity "<RuleName>"
```

In dit voorbeeld wordt de spamfilterregel uitgeschakeld met de naam Marketing Department.

```PowerShell
Disable-HostedContentFilterRule -Identity "Marketing Department"
```

In dit voorbeeld wordt dezelfde regel ingeschakeld.

```PowerShell
Enable-HostedContentFilterRule -Identity "Marketing Department"
```

Zie [Enable-HostedContentFilterRule](/powershell/module/exchange/enable-hostedcontentfilterrule) en [Disable-HostedContentFilterRule](/powershell/module/exchange/disable-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-set-the-priority-of-spam-filter-rules"></a>PowerShell gebruiken om de prioriteit van spamfilterregels in te stellen

De hoogste prioriteit die u in kunt stellen op een regel is 0. De laagste prioriteit die u kunt instellen is afhankelijk van het aantal regels. Als u bijvoorbeeld vijf regels hebt, kunt u de waarden 0 t/m 4 gebruiken. Het wijzigen van de prioriteit van een bestaande regel kan een domino-effect hebben op andere regels. Als u bijvoorbeeld vijf aangepaste regels hebt (prioriteiten 0 t/m 4) en u wijzigt de prioriteit van een regel in 2, dan wordt de bestaande regel met prioriteit 2 gewijzigd in 3 en de regel met prioriteit 3 wordt gewijzigd in 4.

Gebruik de volgende syntaxis om de prioriteit van een spamfilterregel in te stellen in PowerShell:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" -Priority <Number>
```

In dit voorbeeld wordt de prioriteit van de regel met de naam Marketing Department ingesteld op 2. Alle bestaande regels die een prioriteit hebben die minder of gelijk is aan 2, worden verlaagd met 1 (hun prioriteitsnummers worden verhoogd met 1).

```PowerShell
Set-HostedContentFilterRule -Identity "Marketing Department" -Priority 2
```

**Opmerkingen**:

- Als u de prioriteit wilt instellen van een nieuwe regel wanneer u deze maakt, gebruikt u in plaats daarvan de parameter _Prioriteit_ in het cmdlet **New-HostedContentFilterRule**.
- Het standaardbeleid heeft geen bijbehorende spamfilterregel en heeft altijd de waarde **Laagste** die niet kan worden gewijzigd.

### <a name="use-powershell-to-remove-spam-filter-policies"></a>PowerShell gebruiken om spamfilterbeleid te verwijderen

Wanneer u PowerShell gebruikt om spamfilterbeleid te verwijderen, wordt de bijbehorende spamfilterregel niet verwijderd.

Gebruik deze syntaxis om spamfilterbeleid in PowerShell te verwijderen:

```PowerShell
Remove-HostedContentFilterPolicy -Identity "<PolicyName>"
```

In dit voorbeeld wordt het spamfilterbeleid verwijderd met de naam Marketing Department.

```PowerShell
Remove-HostedContentFilterPolicy -Identity "Marketing Department"
```

Zie [Remove-HostedContentFilterPolicy](/powershell/module/exchange/remove-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-remove-spam-filter-rules"></a>PowerShell gebruiken om spamfilterregels te verwijderen

Wanneer u PowerShell gebruikt om een spamfilterregel te verwijderen, wordt het bijbehorende spamfilterbeleid niet verwijderd.

Gebruik deze syntaxis om een spamfilterregel in PowerShell te verwijderen:

```PowerShell
Remove-HostedContentFilterRule -Identity "<PolicyName>"
```

In dit voorbeeld wordt de spamfilterregel verwijderd met de naam Marketing Department.

```PowerShell
Remove-HostedContentFilterRule -Identity "Marketing Department"
```

Zie [Remove-HostedContentFilterRule](/powershell/module/exchange/remove-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Een GTUBE-bericht zenden om de instellingen van uw spambeleid te testen

> [!NOTE]
> Deze stappen werken alleen als het e-mailbedrijf waarvandaan u het GTUBE-bericht stuurt, niet scant op uitgaande spam. Als dit wel het geval is, kunt u het testbericht niet verzenden.

GTUBE (Generic Test for Unsolicited Bulk Email) is een tekenreeks die u opneemt in een testbericht om de antispaminstellingen van uw bedrijf te verifiëren. Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.

Neem de volgende GTUBE-tekst op in een e-mailbericht op één regel zonder spaties of regeleinden:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```
