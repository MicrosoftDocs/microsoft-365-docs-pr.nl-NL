---
title: Berichten en bestanden in quarantaine beheren als beheerder
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe beheerders in quarantaine geplaatste berichten en bestanden voor gebruikers in Office 365 kunnen beheren.
ms.openlocfilehash: e69887b54b3e892775c16fa3e306da3b17ab7db3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036171"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator"></a>In quarantaine geplaatste berichten en bestanden beheren als beheerder

Potentieel gevaarlijke of ongewenste berichten worden in quarantaine geplaatst in Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken. Zie [Quarantaine in Office 365](quarantine-email-messages.md) voor meer informatie.

Beheerders kunnen alle soorten in quarantaine geplaatste berichten voor alle gebruikers bekijken, vrijgeven en verwijderen. Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met een hoog vertrouwen of als gevolg van regels voor e-mailstroom (ook wel transportregels genoemd). Beheerders kunnen ook fout-positieven melden aan Microsoft.

Beheerders in organisaties met Office 365 Advance Threat Protection (ATP) kunnen ook in quarantaine geplaatste bestanden bekijken, downloaden en verwijderen in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.

U bekijkt en beheert in quarantaine geplaatste berichten in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-klanten; Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen. Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie Verbinding maken met Exchange [Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u verbinding wilt maken met Exchange Online Protection PowerShell.

- U moet machtigingen krijgen voordat u de quarantaine als beheerder beheren. De machtigingen worden beheerd door de functie **Quarantaine** in het Security & Compliance Center. Deze rol is standaard toegewezen aan de rolgroepen **Organisatiebeheer** (Globale beheerders), **Quarantainebeheerder**en **Beveiligingsbeheerder** in het Beveiligingscentrum & Compliance Center. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- In quarantaine geplaatste berichten worden standaard bewaard voordat ze automatisch worden verwijderd:

  - Berichten in quarantaine geplaatst door antispambeleid (spam, phishing en bulke-mail): 30 dagen. Dit is de standaard- en maximale waarde. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md)om deze waarde te configureren.

1. Als u een werk- of schoolaccount gebruikt met algemene beheerdersbevoegdheden (of de juiste functies van het Beveiligingscentrum & Compliance Center) in uw organisatie, u zich aanmelden en [naar het Security & Compliance Center gaan.](../../compliance/go-to-the-securitycompliance-center.md)

  - Berichten die malware bevatten: 15 dagen.

  Wanneer een bericht uit quarantaine verloopt, u het bericht niet herstellen.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Het Beveiligings& Compliance Center gebruiken om in quarantaine geplaatste e-mailberichten te beheren

### <a name="view-quarantined-email"></a>In quarantaine geplaatste e-mail weergeven

1. Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.

2. Controleer of **Weergave in quarantaine** is ingesteld op de **standaardwaarde-e-mail**.

3. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):

   - **Ontvangen**<sup>\*</sup>

   - **Afzender**<sup>\*</sup>

   - **Onderwerp**<sup>\*</sup>

   - **Reden van quarantaine**<sup>\*</sup>

   - **Vrijgegeven?**<sup>\*</sup>

   - **Beleidstype**<sup>\*</sup>

1. Als u een werk- of schoolaccount gebruikt met algemene beheerdersbevoegdheden (of de juiste functies van het Beveiligingscentrum & Compliance Center) in uw organisatie, u zich aanmelden en [naar het Security & Compliance Center gaan.](../../compliance/go-to-the-securitycompliance-center.md)

   - **Ontvanger**

   - **Bericht-ID**

   - **Beleidsnaam**

   - **Grootte**

   - **Richting**

   Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.

4. Klik op **Filter** om de resultaten te filteren. De beschikbare filters zijn:

   - **Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:

     - **Vandaag**

     - **Komende 2 dagen**

     - **Komende 7 dagen**

     - **Aangepast**: voer een **begindatum** en **einddatum** in.

   - **Ontvangen op**: voer een **begindatum** en**einddatum** in.

   - **Reden van quarantaine**:

     - **Beleid:** het bericht kwam overeen met de voorwaarden van een regel voor e-mailstroom (ook wel een transportregel genoemd).

     - **Bulk**

     - **Phish**

     - **Malware**

     - **Spam**

     - **Hoog vertrouwen Phish**

   - **E-mailontvanger:** alle gebruikers of alleen berichten die naar u worden verzonden. Eindgebruikers kunnen alleen in quarantaine geplaatste berichten beheren die naar hen worden verzonden.

   Als u het filter wilt wissen, drukt u op **Wissen**. Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.

5. Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken. Jokertekens worden niet ondersteund. U kunt zoeken op een van de volgende waarden:

   - **Bericht-ID**: de wereldwijd unieke identificatie van het bericht.

        U hebt bijvoorbeeld [berichttracering](message-trace-scc.md) gebruikt om te zoeken naar een bericht dat naar een gebruiker in uw organisatie is verzonden en u bepaalt dat het bericht in quarantaine is geplaatst in plaats van geleverd. Zorg ervoor dat u de volledige bericht-ID-waarde\<\>opneemt, waaronder mogelijk hoekhaakjes ( ). Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **E-mailadres afzender**: een enkel e-mailadres van een afzender.

   - **E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.

   - **Onderwerp**: gebruik het volledige onderwerp van het bericht. De zoekopdracht is niet hoofdlettergevoelig.

   Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.

Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).

#### <a name="export-message-results"></a>Berichtresultaat exporteren

1. Selecteer de berichten waarin u bent geïnteresseerd en klik op **Resultaten exporteren**.

2. Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.

3. Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.

#### <a name="view-quarantined-message-details"></a>Gegevens van bericht in quarantaine bekijken

Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:

- **Bericht-ID**: de wereldwijd unieke identificatie van het bericht.

- **Adres afzender**

- **Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.

- **Onderwerp**

- **Quarantainereden:** geeft aan of een bericht is geïdentificeerd als **Spam**, **Bulk**, **Phish,** een e-mailstroomregel **(transportregel)** of is geïdentificeerd als **malware**.

- **Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.

- **Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.

- **Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.

- **Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.

### <a name="take-action-on-quarantined-email"></a>Actie ondernemen op e-mail in quarantaine

Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u met de berichten moet doen in het deelvenster **Flyout Details:**

- **Releasebericht:** kies in het deelvenster flyout dat wordt weergegeven de volgende opties:

  - **Berichten rapporteren aan Microsoft voor analyse:** dit is standaard geselecteerd en rapporteert het ten onrechte in quarantaine geplaatste bericht aan Microsoft als een fout-positief. Als het bericht in quarantaine is geplaatst als spam, bulk, phishing of malware, wordt het bericht ook gerapporteerd aan het Microsoft Spam Analysis Team. Afhankelijk van hun analyse kunnen de regels voor spamfilters voor de hele service worden aangepast om het bericht door te laten gaan.

  - Kies een van de volgende opties:

    - **Berichten vrijgeven aan alle ontvangers**

    - **Berichten vrijgeven aan specifieke ontvangers**

    - **Berichten vrijgeven aan andere mensen**

  Klik op **Berichten vrijgeven** wanneer u gereed bent.

  Opmerkingen over het vrijgeven van berichten:

  - U een bericht niet meer dan één keer aan dezelfde ontvanger vrijgeven.

  - Alleen ontvangers die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële ontvangers.

- **Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken. Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien). Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:

- **Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:

  - **Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.
  
  - **Tekstweergave**: toont het bericht in gewone tekst.

- **Uit quarantaine verwijderen**: Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd zonder naar de oorspronkelijke geadresseerden te worden verzonden.

- **Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.

- **Bericht verzenden:** kies in het deelvenster flyout dat wordt weergegeven de volgende opties:

  - **Objecttype**: **E-mail** (standaard), **URL**of **bijlage**.

  - **Indieningsindeling**: **Netwerkbericht-id** (standaard, met de bijbehorende waarde in het vak **Netwerkbericht-id)** of **Bestand** (blader naar een lokaal .eml- of .msg-bestand). Houd er rekening mee dat als u **Bestand** selecteert en vervolgens **Netwerkbericht-id**selecteert, de oorspronkelijke waarde is verdwenen.

  - **Ontvangers**: Typ bij lease een oorspronkelijke ontvanger van het bericht of klik op **Alles selecteren** om alle geadresseerden te identificeren. U ook op **Alles selecteren** klikken en vervolgens afzonderlijke ontvangers selectief verwijderen.

  - **Reden voor indiening**: **Had niet moeten worden geblokkeerd** (standaard) of had moeten worden **geblokkeerd**.

  Klik op **Verzenden als**u klaar bent.

Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Actie ondernemen op meerdere e-mailberichten in quarantaine

Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:

- **Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.

- **Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.

Klik op **Sluiten** wanneer u gereed bent.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Alleen ATP: het Beveiligingscentrum & compliance gebruiken om in quarantaine geplaatste bestanden te beheren

> [!NOTE]
> De procedures voor in quarantaine geplaatste bestanden in deze sectie zijn alleen beschikbaar voor abonnees van ATP Plan 1 en Plan 2.

In organisaties met ATP kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.

### <a name="view-quarantined-files"></a>In quarantaine geplaatste bestanden weergeven

1. Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.

2. **Weergave wijzigen in quarantaine geplaatst** in de standaardwaardebestanden . **files** U sorteren op een veld door te klikken op een beschikbare kolomkop.

3. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. De standaardkolommen zijn gemarkeerd met<sup>\*</sup>een sterretje :

   - **Gebruiker**<sup>\*</sup>

   - **Locatie**<sup>\*</sup>

   - **Bestandsnaam**<sup>\*</sup>

   - **URL van bestand**<sup>\*</sup>

   - **Bestandsgrootte**<sup>\*</sup>

   - **Vervalt op**<sup>\*</sup>

   - **Vrijgegeven?**<sup>\*</sup>

   - **Gedetecteerd door**

   - **Gewijzigd door tijd**

4. Klik op **Filter** om de resultaten te filteren. De beschikbare filters zijn:

   - **Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:

     - **Vandaag**

     - **Komende 2 dagen**

     - **Komende 7 dagen**

     - Een aangepast datum-/tijdbereik.

   - **Ontvangen tijd**

   - **Quarantaine reden:** De enige beschikbare waarde is **Malware**.

Nadat u een specifiek bestand in quarantaine hebt gevonden, selecteert u het bestand om details erover weer te geven en actie te ondernemen (bijvoorbeeld het bericht bekijken, vrijgeven, downloaden of verwijderen).

#### <a name="export-file-results"></a>Bestandsresultaten exporteren

1. Selecteer de bestanden waarin u geïnteresseerd bent en klik op **Resultaten exporteren**.

2. Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.

3. Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.

#### <a name="view-quarantined-file-details"></a>Bestandsgegevens in quarantaine weergeven

Wanneer u een bestand in de lijst selecteert, worden de volgende bestandsdetails weergegeven in het flyout-deelvenster **Details:**

- **Bestandsnaam**

- **URL van het bestand:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).

- **Schadelijke inhoud gedetecteerd op** De datum/tijd waarop het bestand in quarantaine is geplaatst.

- **Verloopt:** de datum waarop het bestand uit quarantaine wordt verwijderd.

- **Gedetecteerd door**: ATP (Advanced Threat Protection) of Microsoft's anti-malware engine.

- **Vrijgegeven?**

- **Naam malware**

- **Document-id:** een unieke id voor het document.

- **Bestandsgrootte**: In kilobytes (KB).

- **Organisatie** De unieke ID van uw organisatie.

- **Laatst gewijzigd**

- **Gewijzigd door**: De gebruiker die het bestand voor het laatst heeft gewijzigd.

- **Waarde voor Secure Hash Algorithm (SHA-256):** U deze hashwaarde gebruiken om het bestand te identificeren in andere reputatiewinkels of op andere locaties in uw omgeving.

### <a name="take-action-on-quarantined-files"></a>Actie ondernemen voor in quarantaine geplaatste bestanden

Wanneer u een bestand in de lijst selecteert, u de volgende acties in het bestand uitvoeren in het deelvenster **Flyout Details:**

- **Bestanden vrijgeven**: Selecteer (standaard) of schakel De optie **Bestanden rapporteren aan Microsoft uit voor analyse**en klik op Bestanden **vrijgeven**.

- **Bestand downloaden**

- **Bestand uit quarantaine verwijderen**

Als u de bestanden niet vrijgeeft of verwijdert, worden ze verwijderd nadat de standaardbewaartermijn voor quarantaine is verstreken.

#### <a name="actions-on-multiple-quarantined-files"></a>Acties op meerdere in quarantaine geplaatste bestanden

Wanneer u meerdere in quarantaine geplaatste bestanden in de lijst selecteert (maximaal 100), wordt het flyoutvenster **bulkacties** weergegeven waar u de volgende acties uitvoeren:

- **Bestanden vrijgeven**

- **Bestanden verwijderen:** Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de bestanden onmiddellijk verwijderd.

1. Als u een werk- of schoolaccount gebruikt met algemene beheerdersbevoegdheden (of de juiste functies van het Beveiligingscentrum & Compliance Center) in uw organisatie, u zich aanmelden en [naar het Security & Compliance Center gaan.](../../compliance/go-to-the-securitycompliance-center.md)

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell gebruiken om in quarantaine geplaatste berichten en bestanden weer te geven en te beheren

De cmdlets die u gebruikt om berichten en bestanden in quarantaine weer te geven en te beheren, zijn:

- [Bericht verwijderen-quarantaine](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Bericht exporteren-quarantaine](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Bericht in quarantaine plaatsen](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage)Houd er rekening mee dat deze cmdlet alleen is voor berichten, geen malwarebestanden van ATP voor SharePoint Online, OneDrive voor Bedrijven of Teams.

- [Bericht release-quarantaine](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
