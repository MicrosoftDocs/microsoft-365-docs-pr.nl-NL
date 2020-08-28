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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Beheerders kunnen het antispambeleid in Exchange Online Protection (EOP) bekijken, maken, wijzigen en verwijderen.
ms.openlocfilehash: e27e32778f908e85fd4bf0b205e7b80fef798859
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255777"
---
# <a name="configure-anti-spam-policies-in-eop"></a>Antispambeleid configureren in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of standalone EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, zijn binnenkomende e-mailberichten automatisch tegen spam beschermd door EOP. EOP gebruikt antispambeleid (ook wel bekend als spamfilterbeleid of inhoudsfilterbeleid) als onderdeel van de algehele bescherming van uw bedrijf tegen spam. Zie [Bescherming tegen antispam](anti-spam-protection.md) voor meer informatie.

Beheerders kunnen het standaardbeleid bekijken, bewerken en configureren (maar niet verwijderen). Voor grotere nauwkeurigheid kunt u ook aangepast antispambeleid maken dat wordt toegepast op specifieke gebruikers, groepen of domeinen binnen uw bedrijf. Aangepast beleid heeft altijd voorrang op het standaardbeleid, maar u kunt de prioriteit (uitvoervolgorde) wijzigen van uw aangepaste beleid.

U kunt antispambeleid configureren in het Beveiligings- en compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

De basiselementen van antispambeleid zijn: 

- **Het spamfilterbeleid**: omschrijft de acties voor spamfilterbeoordelingen en de meldingsopties.
- **De spamfilterregel**: omschrijft de prioriteits- en geadresseerdenfilters (waarop het beleid van toepassing is) voor spamfilterbeleid.

Het verschil tussen deze twee elementen is niet overduidelijk wanneer u antispambeleid beheert in het Beveiligings- en compliancecentrum:

- Wanneer u antispambeleid maakt, maakt u in feite tegelijkertijd een spamfilterregel en het bijbehorende spamfilterbeleid met dezelfde naam voor beide.
- Wanneer u antispambeleid wijzigt, wordt de spamfilterregel gewijzigd door instellingen met betrekking tot de naam, prioriteit, in- of uitgeschakeld en geadresseerdenfilters. Alle andere instellingen wijzigen het bijbehorende spamfilterbeleid.
- Wanneer u antispambeleid verwijdert, worden de spamfilterregel en het bijbehorende spamfilterbeleid verwijderd.

In Exchange Online PowerShell of standalone EOP PowerShell beheert u het beleid en de regel afzonderlijk. Zie de sectie [Exchange Online PowerShell of standalone EOP PowerShell gebruiken om antispambeleid te configureren](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies) later in dit hoofdstuk voor meer informatie.

Elk bedrijf heeft een ingebouwd antispambeleid met de naam Standaard met de volgende eigenschappen:

- Het beleid wordt toegepast op alle geadresseerden in het bedrijf, ook al is er geen spamfilterregel (geadresseerdenregels) gekoppeld aan het beleid.
- Het beleid heeft de prioriteit **Laagste** die u niet kunt wijzigen (het beleid wordt altijd als laatste toegepast). Alle beleid dat u maakt heeft altijd een hogere prioriteit.
- Het beleid is het standaardbeleid (de eigenschap **IsDefault** heeft de waarde `True`) en u kunt het standaardbeleid niet verwijderen.

Om de effectiviteit van spamfilters te verhogen, kunt u aangepast antispambeleid maken met strengere instellingen dat wordt toegepast op specifieke gebruikers of groepen gebruikers.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Gebruik <https://protection.office.com/antispam> om direct naar de pagina **Antispaminstellingen** te gaan.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:

  - U moet lid zijn van een van de volgende rolgroepen om een antispambeleid toe te voegen, te wijzigen en te verwijderen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezentoegang tot het antispambeleid moet u lid zijn van een van de volgende rollengroepen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Zie [Instellingen voor antispambeleid in EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)voor de aanbevolen instellingen voor antispambeleid.

## <a name="use-the-security--compliance-center-to-create-anti-spam-policies"></a>Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te maken

Wanneer u antispambeleid maakt in het Beveiligings- en compliancecentrum worden tegelijkertijd een spamfilterregel en het bijbehorende spamfilterbeleid gemaakt met dezelfde naam voor beide.

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Kies op de pagina **Antispaminstellingen** op **Beleid maken**.

3. Configureer in het deelvenster **Nieuw spamfilterbeleid** dat wordt geopend de volgende instellingen:

   - **Naam**: een unieke beschrijvende naam voor het beleid. U mag de volgende tekens niet gebruiken: `\ % & * + / = ? { } | < > ( ) ; : , [ ] "`.

      Als u eerder al antispambeleid hebt gemaakt in het Exchange-beheercentrum (EAC) dat deze tekens bevat, moet u het antispambeleid in PowerShell hernoemen. Zie de sectie [PowerShell gebruiken om spamfilterregels te wijzigen](#use-powershell-to-modify-spam-filter-rules) verderop in dit artikel voor instructies.

   - **Beschrijving**: voer een optionele beschrijving in voor het beleid.

4. (Optioneel) Vouw de sectie **Spam- en bulkbewerkingen** uit en controleer of configureer de volgende instellingen:

   - **Selecteer de actie die moet worden uitgevoerd voor binnenkomende spam en bulk-e-mail**: selecteer of bekijk de actie die moet worden uitgevoerd op berichten op basis van de volgende spamfilterbeoordelingen:

     - **Spam**
     - **Hoogstwaarschijnlijk spam**
     - **Phishing-e-mail**
     - **Hoogstwaarschijnlijk Phishing-e-mail**
     - **Bulk-e-mail**

     De beschikbare acties voor spamfilterbeoordelingen worden beschreven in de volgende tabel.

     - Een vinkje ( ![vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) geeft aan dat de actie beschikbaar is (niet alle acties zijn beschikbaar voor alle spamfilterbeoordelingen).
     - Een asterisk (<sup>\*</sup>) na het vinkje geeft de standaardactie aan voor de spamfilterbeoordeling. 

     ****

     |<span>|Spam|Hoog<br/>betrouwbaarheid<br/>spam|Phishing<br/>e-mail|Hoog<br/>betrouwbaarheid<br/>phishing<br/>e-mail|Bulk<br/>e-mail|
     |---|:---:|:---:|:---:|:---:|:---:|
     |**Bericht verplaatsen naar de map Ongewenste e-mail**: het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail.<sup>1</sup>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**X-kop toevoegen**: hiermee wordt een X-kop toegevoegd aan de berichtkop en het bericht bezorgd in het postvak. <br/> U voert de veldnaam (niet de waarde) van de X-kop later in het vak **Deze X-koptekst toevoegen** in.  <br/><br/> Bij de beoordelingen **Spam** en **Hoogstwaarschijnlijk spam** wordt het bericht verplaatst nar de map Ongewenste e-mail.<sup>1,2</sup>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
     |**Onderwerpregel vooraan uitbreiden met tekst**: hiermee wordt tekst toegevoegd aan het begin van de onderwerpregel van het bericht. Het bericht wordt bezorgd in het postvak en verplaatst naar de map Ongewenste e-mail.<sup>1,2</sup> <br/> U voert de tekst later in het vak **Voeg deze tekst toe vooraan de onderwerpregel** in.|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Bericht naar e-mailadres omleiden**: hiermee wordt het bericht omgeleid naar andere geadresseerden in plaats van de beoogde geadresseerde. <br/> U geeft de geadresseerden later op in het vak **Omleiden naar dit e-mailadres**.|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Bericht verwijderen**: hiermee wordt het volledige bericht verwijderd, inclusief alle bijlagen.|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Bericht in quarantaine**: hiermee wordt het bericht in quarantaine geplaatst in plaats van verzonden naar de beoogde geadresseerden. <br/> U geeft later in het vak **Quarantaine** aan hoelang het bericht in quarantaine moet blijven.|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |**Geen actie**|||||![Vinkje](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
     |

     > <sup>1</sup> In Exchange Online wordt het bericht verplaatst naar de map Ongewenste e-mail als de regel Ongewenste e-mail is ingeschakeld voor het postvak (standaard is die regel ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.
     >
     > In standalone EOP-omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail. Zie [Standalone EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) voor meer informatie. 
     >
     > <sup>2</sup> U kunt deze waarde gebruiken als voorwaarde in e-mailstroomregels (ook wel transportregels) om het bericht te filteren of om te leiden.

   - **De drempelwaarde selecteren**: hiermee wordt het bulkklachtniveau (BCL) van een bericht aangegeven dat de gespecificeerde actie activeert voor de **Bulk-e-mail**-spamfilterbeoordeling (groter dan de opgegeven waarde, niet groter dan of gelijk aan). Een hogere waarde geeft aan dat het bericht minder wenselijk is (grotere kans dat het bericht spam is). De standaardwaarde is 7. Zie [Bulkklachtniveau (BCL) in EOP](bulk-complaint-level-values.md) en [Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md) voor meer informatie.

     Standaard is de enige PowerShell-instelling _MarkAsSpamBulkMail_ `On` in antispambeleid. Deze instelling is van grote invloed op de resultaten van een **Bulk-e-mail**-filterbeoordeling:

     - **_MarkAsSpamBulkMail_ is ingeschakeld**: een BCL dat groter is dan de drempelwaarde wordt geconverteerd naar een SCL 6, wat overeenkomt met een filterbeoordeling van **Spam** en de actie voor de **Bulk-e-mail**-filterbeoordeling wordt toegepast op het bericht.

     - **_MarkAsSpamBulkMail_ is uitgeschakeld**: het bericht krijgt het stempel BCL, maar er wordt _geen actie_ uitgevoerd voor een **Bulk-e-mail**-filterbeoordeling. Het gevolg is dat de BCL-drempelwaarde en de actie voor de **Bulk-e-mail**-filterbeoordeling niet relevant zijn.

   - **Quarantaine**: geeft aan hoe lang het bericht in quarantaine moet worden gehouden als u de actie **Bericht in quarantaine plaatsen** hebt geselecteerd voor een spamfilterbeoordeling. Na het verlopen van de periode wordt het bericht verwijderd. De standaardwaarde is 30 dagen. Een geldige waarde ligt tussen de 1 en 30 dagen. Zie de volgende artikelen voor meer informatie over quarantaine:

     - [Berichten in quarantaine in EOP](quarantine-email-messages.md)
     - [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md)
     - [Berichten in quarantaine zoeken en vrijgeven als gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)

   - **Deze X-koptekst toevoegen**: dit vak is alleen vereist en beschikbaar als u de actie **X-kop toevoegen** hebt geselecteerd voor een spamfilterbeoordeling. De waarde die u opgeeft, is de naam van het *kopveld* dat wordt toegevoegd aan de berichtkop. De kopveld*waarde* is altijd `This message appears to be spam`.

     De maximumlengte is 255 tekens en de waarde kan geen spaties of dubbele punten (:) bevatten.

     Als u bijvoorbeeld de waarde `X-This-is-my-custom-header` opgeeft, wordt de X-kop `X-This-is-my-custom-header: This message appears to be spam.` toegevoegd aan het bericht.

     Als u een waarde opgeeft die spaties of dubbele punten (:) bevat, wordt de ingevoerde waarde genegeerd en wordt de standaard-X-kop (`X-This-Is-Spam: This message appears to be spam.`) aan het bericht toegevoegd.

   - **Onderwerpregel vooraan uitbreiden met deze tekst**: dit vak is alleen vereist en beschikbaar als u de actie **Onderwerpregel vooraan uitbreiden met tekst** hebt geselecteerd voor een spamfilterbeoordeling. Voer de tekst in die moet worden toegevoegd aan het begin van de onderwerpregel van het bericht.

   - **Bericht naar dit e-mailadres omleiden**: dit vak is alleen vereist en beschikbaar als u de actie **Bericht naar e-mailadres omleiden** hebt geselecteerd voor een spamfilterbeoordeling. Voer het e-mailadres in waarnaar u het bericht wilt verzenden. U kunt meerdere waarden opgeven, gescheiden door puntkomma’s (;).

   - **Veiligheidstips**: standaard staan veiligheidstips ingeschakeld, maar u kunt ze uitschakelen door het selectievakje **Aan** uit te schakelen. Zie [Veiligheidstips in e-mailberichten](safety-tips-in-office-365.md) voor meer informatie over veiligheidstips.

   **Zero-hour auto purge**-instellingen: ZAP detecteert en voert actie uit op berichten die al zijn afgeleverd aan Exchange Online-postvakken. Zie [Zero-hour auto purge - beveiliging tegen ongewenste e-mail en malware](zero-hour-auto-purge.md) voor meer informatie over ZAP.

   - **Spam ZAP**: ZAP is standaard ingeschakeld voor spamdetectie, maar u kunt het uitschakelen door het selectievakje **Aan** uit te schakelen.

   - **Phish ZAP**: ZAP is standaard ingeschakeld voor phishingdetectie, maar u kunt het uitschakelen door het selectievakje **Aan** uit te schakelen.

5. (Optioneel) Vouw de sectie **Lijsten toestaan** uit om op basis van e-mailadres of e-maildomein afzenders van berichten te configureren die de spamfilters mogen overslaan:

   > [!CAUTION]
   >
   > - Denk goed na voordat u hier domeinen toevoegt. Zie [Lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md) voor meer informatie.
   >
   > - Voeg nooit geaccepteerde domeinen (domeinen waarvan u eigenaar bent) of algemene domeinen (bijv.: microsoft.com of office.com) toe aan de lijst met toegestane domeinen. Hiermee kunnen kwaadwillende gebruikers e-mail verzenden die de e-mailspamfilters in uw bedrijf overslaat.

   - **Afzender toelaten**: klik op **Bewerken**. In het deelvenster **Lijst met toegestane afzenders** dat wordt weergegeven:

      a. Voert u het e-mailadres van de afzender in. U kunt meerdere e-mailadressen opgeven, gescheiden door puntkomma’s (;).

      b. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de afzenders toe te voegen.

      Herhaal deze stappen zo vaak als nodig is.

      De afzenders die u hebt toegevoegd worden weergegeven in de sectie **Toegestane afzenders** in het deelvenster. Om een afzender te verwijderen, klikt u op ![Pictogram verwijderen](../../media/scc-remove-icon.png).

      Klik op **Opslaan** wanneer u gereed bent.

   - **Domein toelaten**: klik op **Bewerken**. In het deelvenster **Lijst met toegestane domeinen** dat wordt weergegeven:

      a. Voert u het domein in. U kunt meerdere domeinen opgeven, gescheiden door puntkomma’s (;).

      b. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de domeinen toe te voegen.

      Herhaal deze stappen zo vaak als nodig is.

      De domeinen die u hebt toegevoegd worden weergegeven in de sectie **Toegestane domeinen** in het deelvenster. Om een domein te verwijderen, klikt u op ![Pictogram verwijderen](../../media/scc-remove-icon.png).

      Klik op **Opslaan** wanneer u gereed bent.

6. (Optioneel) Vouw de sectie **Geblokkeerd** uit om op basis van e-mailadres of e-maildomein afzenders van berichten te configureren die altijd worden gemarkeerd als Hoogstwaarschijnlijk spam:

   > [!NOTE]
   > Het is niet gevaarlijk handmatig domeinen te blokkeren, maar het kan de werkbelasting vergroten Zie [Lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md) voor meer informatie.

   - **Afzender blokkeren**: klik op **Bewerken**. In het deelvenster **Lijst met geblokkeerde afzenders** dat wordt weergegeven:

      a. Voert u het e-mailadres van de afzender in. U kunt meerdere e-mailadressen opgeven, gescheiden door puntkomma’s (;). Jokertekens (*) worden niet ondersteund.

      b. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de afzenders toe te voegen.

      Herhaal deze stappen zo vaak als nodig is.

      De afzenders die u hebt toegevoegd worden weergegeven in de sectie **Geblokkeerde afzenders** in het deelvenster. Om een afzender te verwijderen, klikt u op de knop ![Verwijderen](../../media/scc-remove-icon.png).

      Klik op **Opslaan** wanneer u gereed bent.

   - **Domein blokkeren**: klik op **Bewerken**. In het deelvenster **Lijst met geblokkeerde domeinen** dat wordt weergegeven:

      a. Voert u het domein in. U kunt meerdere domeinen opgeven, gescheiden door puntkomma’s (;). Jokertekens (*) worden niet ondersteund.

      b. Klikt u op ![Pictogram toevoegen](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) om de domeinen toe te voegen.

      Herhaal deze stappen zo vaak als nodig is.

      De domeinen die u hebt toegevoegd worden weergegeven in de lijst **Geblokkeerde domeinen** in het deelvenster. Om een domein te verwijderen, klikt u op knop ![Verwijderen](../../media/scc-remove-icon.png).

      Klik op **Opslaan** wanneer u gereed bent.

7. (Optioneel) Vouw de sectie **Internationale spam** uit om de e-mailtalen of herkomstlanden te configureren die worden geblokkeerd door spamfilters:

   - **E-mailberichten in de volgende talen filteren**: deze instelling is standaard uitgeschakeld (**Satus: UIT**). Klik op **Bewerken**. Configureer in het deelvenster **Internationale spaminstellingen** dat wordt weergegeven de volgende instellingen:

     - **E-mailberichten in de volgende talen filteren**: selecteer het selectievakje om deze instelling in te schakelen. Schakel het selectievakje uit om deze instelling uit te schakelen.

     - Klik in het vak en begin de *naam* van de taal te typen. Er wordt een gefilterde lijst met ondersteunde talen weergegeven, samen met de bijbehorende ISO 639-2-taalcode. Wanneer u de gezochte taal vindt, selecteert u die. Herhaal deze stap zo vaak als nodig is.

       De lijst met talen die u hebt geselecteerd, verschijnt in het deelvenster. Om een taal te verwijderen, klikt u op ![de knop Verwijderen](../../media/scc-remove-icon.png).

     Klik op **Opslaan** wanneer u gereed bent.

   - **E-mailberichten uit de volgende landen of regio’s filteren**: deze instelling is standaard uitgeschakeld (**Satus: UIT**). Klik op **Bewerken** om de instelling in te schakelen. Configureer in het deelvenster **Internationale spaminstellingen** dat wordt weergegeven de volgende instellingen:

     - **E-mailberichten uit de volgende landen of regio’s filteren**: selecteer het selectievakje om deze instelling in te schakelen. Schakel het selectievakje uit om deze instelling uit te schakelen.

     - Klik in het vak en begin de *naam* van het land of de regio te typen. Er wordt een gefilterde lijst met ondersteunde landen weergegeven, samen met de bijbehorende tweeletterige ISO 3166-1-landcode. Selecteer het land of de regio waarnaar u zocht als het is gevonden. Herhaal deze stap zo vaak als nodig is.

       De lijst met landen die u hebt geselecteerd, verschijnt in het deelvenster. Om een land of regio te verwijderen, klikt u op ![de knop Verwijderen](../../media/scc-remove-icon.png).

     Klik op **Opslaan** wanneer u gereed bent.

8. De optionele sectie **Spameigenschappen** bevat ASF-instellingen (geavanceerde instellingen voor spamfilters) die standaard zijn uitgeschakeld. ASF-instellingen worden afgeschaft en hun functionaliteit wordt opgenomen in andere onderdelen van de filterstack. Het is raadzaam dat u al deze ASF-instellingen uitgeschakeld laat in uw antispambeleid.

   Zie [Geavanceerde instellingen voor spamfilters in EOP](advanced-spam-filtering-asf-options.md) voor meer informatie over deze instellingen.

9. (Verplicht) Vouw de sectie **Toegepast op** uit om de interne geadresseerden te bepalen op wie het beleid van toepassing is.

    U kunt een voorwaarde of uitzondering maar één keer gebruiken, maar u kunt meerdere waarden opgeven voor de voorwaarde of uitzondering. Meerdere waarden van dezelfde voorwaarde of uitzondering: gebruik OF-logica (bijvoorbeeld: _\<recipient1\>_ of _\<recipient2\>_). Verschillende voorwaarden of uitzonderingen: gebruik EN-logica (bijvoorbeeld: _\<recipient1\>_ en _\<member of group 1\>_).

    Het eenvoudigste is drie keer te klikken op **Een voorwaarde toevoegen** om alle beschikbare voorwaarden weer te geven. U kunt op de ![knop Verwijderen](../../media/scc-remove-icon.png) klikken om voorwaarden te verwijderen die u niet wilt configureren.

    - **Het domein van de geadresseerde is**: specificeert geadresseerden in een of meer van de geconfigureerde domeinen in uw organisatie. Klik in het vak **Een tag toevoegen** om een domein weer te geven en te selecteren. Klik opnieuw op het vak **Een tag toevoegen** om aanvullende domeinen te selecteren als er meer dan één domein beschikbaar is.

    - **Geadresseerde is**: specificeert een of meer postvakken, e-mailgebruikers or e-mailcontactpersonen binnen uw bedrijf. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik opnieuw op het vak **Tag toevoegen** om aanvullende geadresseerden te selecteren.

    - **Geadresseerde is een lid van**: specificeert een of meer groepen in uw bedrijf. Klik in het vak **Tag toevoegen** en begin te typen om de lijst te filteren. Klik opnieuw op het vak **Tag toevoegen** om aanvullende geadresseerden te selecteren.

    - **Behalve als**: om uitzonderingen op de regel toe te voegen, klikt u drie keer op **Een voorwaarde toevoegen** om alle beschikbare uitzonderingen weer te geven. De instellingen en het gedrag zijn exact hetzelfde als bij de voorwaarden.

10. Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-view-anti-spam-policies"></a>Het Beveiligings- en compliancecentrum gebruiken om antispambeleid weer te geven

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om antispambeleid uit te vouwen:

   - Het standaardbeleid met de naam **Standaardbeleid voor spamfilters**.

   - Aangepast beleid dat u hebt gemaakt, waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is.

3. De belangrijke beleidsinstellingen worden weergegeven in de uitgebreide beleidsgegevens. Klik op **Beleid bewerken** voor meer gegevens.

## <a name="use-the-security--compliance-center-to-modify-anti-spam-policies"></a>Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te wijzigen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om antispambeleid uit te vouwen:

   - Het standaardbeleid met de naam **Standaardbeleid voor spamfilters**.

   - Aangepast beleid dat u hebt gemaakt, waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is.

3. Klik op **Beleid bewerken**.

De beschikbare instellingen in het deelvenster zijn voor aangepast antispambeleid hetzelfde als die zijn beschreven in de sectie [Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te maken](#use-the-security--compliance-center-to-create-anti-spam-policies).

Voor het standaardantispambeleid met de naam **Standaardbeleid voor spamfilters** is de sectie **Toegepast op** niet beschikbaar (het beleid is op iedereen van toepassing) en u kunt de naam van het beleid niet wijzigen.

Zie de volgende secties om beleid in- of uit te schakelen, de prioriteit van beleid te wijzigen of de quarantaine-meldingen van eindgebruiker configureren.

### <a name="enable-or-disable-anti-spam-policies"></a>Antispambeleid in- of uitschakelen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik in de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om aangepast beleid uit te vouwen dat u hebt gemaakt (de waarde in de kolom **Type** is **Aangepast antispambeleid**).

3. Let op de waarde in de kolom **Aan** in de uitgebreide beleidsgegevens die worden weergegeven.

   Verplaats te wisselknop naar links om het beleid uit te schakelen: ![Uitschakelen](../../media/scc-toggle-off.png)

   Verplaats te wisselknop naar rechts om het beleid in te schakelen: ![Inschakelen](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

U kunt het standaardantispambeleid niet uitschakelen.

### <a name="set-the-priority-of-custom-anti-spam-policies"></a>De prioriteit instellen voor aangepast antispambeleid

Standaard krijgt antispambeleid een prioriteit op basis van de volgorde waarin het is gemaakt (nieuwer beleid heeft een hogere prioriteit dan ouder beleid). Een lager prioriteitsnummer geeft een hogere prioriteit aan voor het beleid (0 is de hoogste) en beleid word verwerkt in prioriteitsvolgorde (beleid met hogere prioriteit wordt verwerkt voor beleid met lagere prioriteit). Twee beleidsregels kunnen niet dezelfde prioriteit hebben en de verwerking van het beleid stopt nadat het eerste beleid is toegepast.

Voor meer informatie over de prioriteitvolgorde en het evalueren en toepassen van een beleid, raadpleegt u [volgorde en prioriteit van e-mailbeveiliging](how-policies-and-protections-are-combined.md).

Aangepast antispambeleid wordt weergegeven in de volgorde waarin het wordt verwerkt (het eerste beleid heeft de **Prioriteit**swaarde 0). Het standaardantispambeleid met de naam **Standaardbeleid voor spamfilters** heeft de prioriteitswaarde **Laagste** en dat kunt u niet wijzigen.

 **Opmerking**: In het Beveiligings- en compliancecentrum kunt u alleen de prioriteit wijzigen van het antispambeleid nadat u het hebt gemaakt. In PowerShell kunt u de standaardprioriteit vervangen wanneer u de spamfilterbeleidsregel maakt (die kan de prioriteit van bestaande regels beïnvloeden).

Om de prioriteit van beleid te wijzigen, kunt u het beleid naar boven of beneden verplaatsen in de lijst (u kunt het **Prioriteit**snummer in het Beveiligings en compliancecentrum niet rechtstreeks wijzigen).

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Zoek in de pagina **Antispaminstellingen**het beleid waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is. Let op de waarden in de kolom **Prioriteit**:

   - Het aangepaste antispambeleid met de hoogste prioriteit heeft de waarde ![Pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Het aangepaste antispambeleid met de laagste prioriteit heeft de waarde ![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) **n** (bijv.: ![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Als u drie of meer aangepaste antispambeleidsregels hebt, hebben de regels tussen de hoogste en laagste prioriteit de waarden ![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png)![Pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) **n** (bijv.: ![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png)![Pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Klik op ![het pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.png) of ![het pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.png) om het aangepaste antispambeleid omhoog of omlaag te verplaatsen in de prioriteitslijst.

### <a name="configure-end-user-spam-notifications"></a>Spammeldingen voor eindgebruikers configureren

Wanneer in een spamfilterbeoordeling een bericht in quarantaine wordt geplaatst, kunt u spammeldingen voor eindgebruikers configureren om geadresseerden te laten weten wat er is gebeurd met berichten die naar hen zijn verzonden. Zie [Spammeldingen voor eindgebruikers in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor meer informatie over deze meldingen.

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik op de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om antispambeleid uit te vouwen:

   - Het standaardbeleid met de naam **Standaardbeleid voor spamfilters**.

   - Aangepast beleid dat u hebt gemaakt, waarvan de waarde in de kolom **Type**, **Aangepast antispambeleid** is.

3. Klik op **Spammeldingen voor eindgebruikers configureren** in de uitgebreide beleidsgegevens die worden weergegeven.

4. Configureer de volgende instellingen in het dialoogvenster **\<Policy Name\>** dat wordt geopend:

   - **Spammeldingen voor eindgebruikers inschakelen**: vink het selectievakje aan om meldingen in te schakelen. Schakel het selectievakje uit om meldingen uit te schakelen.

   - **Iedere (dagen) spammeldingen voor eindgebruikers verzenden **: selecteer hoe vaak meldingen worden verzonden. De standaardwaarde is 3 dagen. U kunt 1 tot 15 dagen opgeven.

     Er zijn drie cycli van spammeldingen voor eindgebruikers binnen een periode van 24 uur die beginnen op de volgende tijden: 01:00 UTC, 08:00 UTC en 16:00 UTC.

     > [!NOTE]
     > Als we tijdens een vorige cyclus een melding hebben gemist, wordt in de volgende cyclus de melding gepusht. Dit geeft de indruk van meerdere meldingen op dezelfde dag.

   - **Taal van meldingen**: klik op de vervolgkeuzelijst en selecteer een beschikbare taal in de lijst. De standaardwaarde is **Standaard**, dat wil zeggen Engels.

   Klik op **Opslaan** wanneer u gereed bent.

## <a name="use-the-security--compliance-center-to-remove-anti-spam-policies"></a>Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te verplaatsen

1. Ga in het Beveiligings- en compliancecentrum naar **Risicobeheer** \> **Beleid** \> **Antispam**.

2. Klik in de pagina **Antispaminstellingen** op ![Pictogram uitvouwen](../../media/scc-expand-icon.png) om het aangepaste beleid uit te vouwen dat u wilt verwijderen (de waarde in de kolom **Type** is **Aangepast antispambeleid**).

3. Klik in de uitgebreide beleidsgegevens op **Beleid verwijderen**.

4. Klik op **Ja** in het waarschuwingsvenster dat wordt weergegeven.

U kunt het standaardbeleid niet verwijderen.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-anti-spam-policies"></a>Exchange Online PowerShell of standalone EOP PowerShell gebruiken om antispambeleid te configureren

Zoals eerder beschreven, bestaat een antispambeleid uit een spamfilterbeleid en een spamfilterregel.

In Exchange Online PowerShell of standalone EOP PowerShell is het verschil tussen spamfilterbeleid en spamfilterregels duidelijk. U beheert spamfilterbeleid door de cmdlets **\*-HostedContentFilterPolicy** te gebruiken en u beheert spamfilterregels door de cmdlets **\*-HostedContentFilterRule** te gebruiken. 

- In PowerShell maakt u eerst het spamfilterbeleid en vervolgens maakt u de spamfilterregel die het beleid identificeert waarop de regel van toepassing is.
- In PowerShell wijzigt u de instellingen in het spamfilterbeleid en de spamfilterregel afzonderlijk.
- Wanneer u spamfilterbeleid verwijdert uit PowerShell, wordt de bijbehorende spamfilterregel niet automatisch verwijderd en omgekeerd.

De volgende antispambeleidsinstellingen zijn alleen beschikbaar in PowerShell:

- De parameter _MarkAsSpamBulkMail_, die standaard `On` is. De gevolgen van deze instelling zijn eerder in dit artikel uitgelegd in de sectie [Het Beveiligings- en compliancecentrum gebruiken om antispambeleid te maken](#use-the-security--compliance-center-to-create-anti-spam-policies).

- De volgende instellingen voor quarantainemeldingen voor eindgebruikers:

  - De parameter_DownloadLink_ toont of verbergt de koppeling naar het rapportagehulpmiddel voor ongewenste e-mail voor Outlook.

  - De parameter _EndUserSpamNotificationCustomSubject_ die u kunt gebruiken om de onderwerpregel van de melding aan te passen.

### <a name="use-powershell-to-create-anti-spam-policies"></a>PowerShell gebruiken om antispambeleid te maken

Antispambeleid maken in PowerShell bestaat uit twee stappen:

1. Het spamfilterbeleid maken.
2. De spamfilterbeleidsregel maken die het spamfilterbeleid opgeeft waarop de regel van toepassing is.

 **Opmerkingen**:

- U kunt een nieuwe spamfilterbeleidsregel maken en een bestaand, niet-gekoppeld spamfilterbeleid eraan toewijzen. Een spamfilterbeleidsregel kan niet worden gekoppeld aan meer dan één spamfilterbeleid.

- U kunt de volgende instellingen voor nieuw spamfilterbeleid configureren in PowerShell die niet beschikbaar zijn in het Beveiligings- en compliancecentrum tot nadat u het beleid hebt gemaakt:

  - Schakel het nieuwe beleid uit (_Ingeschakeld_ `$false` in het cmdlet **New-HostedContentFilterRule**).
  - Stel de prioriteit van het beleid in tijdens het maken (_Prioriteit_ _\<Number\>_) in de cmdlet **New-HostedContentFilterRule**).

- Nieuw spamfilterbeleid dat u maakt in PowerShell is niet zichtbaar in het Beveiligings- en compliancecentrum totdat u het beleid toewijst aan een spamfilterregel.

#### <a name="step-1-use-powershell-to-create-a-spam-filter-policy"></a>Stap 1: PowerShell gebruiken om spamfilterbeleid te maken

Gebruik de volgende syntaxis om spamfilterbeleid te maken:

```PowerShell
New-HostedContentFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

Dit voorbeeld maakt spamfilterbeleid met de naam Contoso Executives met de volgende instellingen:

- Quarantainemeldingen wanneer de spamfilterbeoordeling Spam of Hoogstwaarschijnlijk spam is.

- BCL 6 activeert de actie voor een bulk-e-mail-spamfilterbeoordeling.

```PowerShell
New-HostedContentFilterPolicy -Name "Contoso Executives" -HighConfidenceSpamAction Quarantine -SpamAction Quarantine -BulkThreshold 6
```

> [!NOTE]
> **New-HostedContentFilterPolicy** en **Set-HostedContentFilterPolicy** bevatten een oudere parameter _ZapEnabled_ en nieuwere parameters_PhishZapEnabled_ en _SpamZapEnabled_. De parameter _ZapEnabled_ is in februari 2020 afgeschaft. The parameters _PhishZapEnabled_ en _SpamZapEnabled_ namen hun waarden over van de parameter _ZapEnabled_. Maar als u de parameters _PhishZapEnabled_ en _SpamZapEnabled_ gebruikt in een opdracht of de instelling **Spam ZAP** of **Phish ZAP** in het antispambeleid in het Beveiligings- en compliancecentrum, wordt de waarde van de parameter _ZapEnabled_ genegeerd. Met andere woorden, gebruik de parameter _ZapEnabled_ niet, maar gebruik hiervoor in de plaats de parameters _PhishZapEnabled_ en _SpamZapEnabled_.

Zie [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

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

Zie [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

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

Zie [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

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

Zie [Get-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-spam-filter-policies"></a>PowerShell gebruiken om spamfilterbeleid te wijzigen

Voor het wijzigen van spamfilterbeleid in PowerShell kunt u, naast de volgende items, beschikken over dezelfde instellingen als bij het maken van het beleid zoals eerder in dit artikel beschreven in de sectie [Stap 1: PowerShell gebruiken om spamfilterbeleid te maken](#step-1-use-powershell-to-create-a-spam-filter-policy).

- De schakeloptie _MakeDefault_ die het specifieke beleid wijzigt in het standaardbeleid (toegepast op iedereen, altijd **Laagste** prioriteit en kan niet worden verwijderd) is alleen beschikbaar wanneer u spamfilterbeleid wijzigt in PowerShell.

- U kunt de naam van het spamfilterbeleid niet wijzigen (het cmdlet **Set-HostedContentFilterPolicy** heeft geen parameter _Naam_). Wanneer u de naam van antispambeleid in het Beveiligings- en compliancecentrum wijzigt, wijzigt u alleen de naam van de spamfilter_regel_.

Gebruik de volgende syntaxis om spamfilterbeleid te wijzigen:

```PowerShell
Set-HostedContentFilterPolicy -Identity "<PolicyName>" <Settings>
```

Zie [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

### <a name="use-powershell-to-modify-spam-filter-rules"></a>PowerShell gebruiken om spamfilterregels te wijzigen

De enige instelling die niet beschikbaar is wanneer u een spamfilterregel wijzigt in PowerShell, is de parameter _Ingeschakeld_ waarmee u een uitgeschakelde regel kunt maken. Zie de volgende sectie om bestaande spamfilterregels in of uit te schakelen.

Er zijn geen extra instellingen beschikbaar wanneer u een spamfilterregel wijzigt in PowerShell. Dezelfde instellingen zijn beschikbaar wanneer u een regel maakt zoals eerder in dit artikel beschreven in de sectie [Stap 2: PowerShell gebruiken om een spamfilterregel te maken](#step-2-use-powershell-to-create-a-spam-filter-rule).

Gebruik de volgende syntaxis om een spamfilterregel te wijzigen:

```PowerShell
Set-HostedContentFilterRule -Identity "<RuleName>" <Settings>
```

In dit voorbeeld wordt de naam veranderd van de bestaande spamfilterregel met de naam `{Fabrikam Spam Filter}` die problemen kan veroorzaken in het Beveiligings- en compliancecentrum.

```powershell
Set-HostedContentFilterRule -Identity "{Fabrikam Spam Filter}" -Name "Fabrikam Spam Filter"
```

Zie [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

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

Zie [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedcontentfilterrule) en [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

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

Zie [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterpolicy) voor gedetailleerde syntaxis- en parameterinformatie.

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

Zie [Remove-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedcontentfilterrule) voor gedetailleerde syntaxis- en parameterinformatie.

## <a name="how-do-you-know-these-procedures-worked"></a>Hoe weet ik of deze procedures zijn geslaagd?

### <a name="send-a-gtube-message-to-test-your-spam-policy-settings"></a>Een GTUBE-bericht zenden om de instellingen van uw spambeleid te testen

> [!NOTE]
> Deze stappen werken alleen als het e-mailbedrijf waarvandaan u het GTUBE-bericht stuurt, niet scant op uitgaande spam. Als het bedrijf dat wel doet, kan het testbericht niet worden verzonden.

GTUBE (Generic Test for Unsolicited Bulk Email) is een tekenreeks die u opneemt in een testbericht om de antispaminstellingen van uw bedrijf te verifiëren. Een GTUBE-bericht is vergelijkbaar met het EICAR-tekstbestand (European Institute for Computer Antivirus Research) voor het testen van malware-instellingen.

Neem de volgende GTUBE-tekst op in een e-mailbericht op één regel zonder spaties of regeleinden:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="allowblock-lists"></a>Lijsten toestaan/blokkeren

Er zijn momenten waarop de filters het bericht missen of het duurt even voor de systemen helemaal bijgewerkt zijn. In die gevallen heeft het antispambeleid een lijst Toestaan en een lijst Blokkeren beschikbaar om de huidige beoordeling te negeren. Deze optie moet spaarzaam en tijdelijk worden gebruikt, omdat de lijsten onbeheerbaar kunnen worden, omdat de filterstack moet doen waarvoor die is ingesteld.

> [!TIP]
> Er kunnen situaties zijn waar uw bedrijf het niet eens is met de beoordeling die de service aflevert. In dat geval wilt u mogelijk de lijsten Toestaan en Blokkeren permanent behouden. Als u echter een domein voor een langere periode op de lijst Toestaan plaatst, moet u dat de afzender laten weten om zeker te weten dat het domein is geverifieerd en instellen op DMARC als dat niet zo is.
