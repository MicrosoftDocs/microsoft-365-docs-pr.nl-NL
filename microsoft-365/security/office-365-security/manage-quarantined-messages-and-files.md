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
description: Beheerders kunnen in Exchange Online Protection (EOP) leren hoe ze in quarantaine geplaatste berichten voor alle gebruikers kunnen bekijken en beheren. Beheerders in organisaties met Office 365 Advanced Threat Protection (Office 365 ATP) kunnen ook bestanden in quarantaine beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.openlocfilehash: 5e7c594669cf910404badd85c35671c284d4d91e
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101679"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Berichten en bestanden in quarantaine beheren als EOP-beheerder

In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst. Zie [EOP in quarantaine geplaatst](quarantine-email-messages.md)voor meer informatie.

Beheerders kunnen alle typen in quarantaine geplaatste berichten voor alle gebruikers bekijken, vrijgeven en verwijderen. Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met veel vertrouwen of als gevolg van regels voor e-mailstromen (ook wel transportregels genoemd). Beheerders kunnen ook fout-positieven melden aan Microsoft.

Beheerders in organisaties met Office 365 Advance Threat Protection (Office 365 ATP) kunnen ook in quarantaine geplaatste bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams bekijken, downloaden en verwijderen.

U bekijkt en beheert in quarantaine geplaatste berichten in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; standalone EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen. Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet machtigingen krijgen voordat u de quarantaine als beheerder beheren. De machtigingen worden beheerd door de **quarantainerol** in het Security & Compliance Center. Standaard wordt deze rol toegewezen aan de **rolgroepen Organisatiebeheer** (Globale beheerders), **Quarantainebeheerder**en **Beveiligingsbeheerder** in het Security & Compliance Center. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- In quarantaine geplaatste berichten worden gedurende een standaardperiode bewaard voordat ze automatisch worden verwijderd:

  - Berichten die in quarantaine zijn geplaatst via het antispambeleid (spam, phishing en bulke-mail): 30 dagen. Dit is de standaard- en maximale waarde. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md)als u deze waarde wilt configureren.

  - Berichten die malware bevatten: 15 dagen.

  Wanneer een bericht uit quarantaine verloopt, u het bericht niet herstellen.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Gebruik het Security & Compliance Center om e-mailberichten in quarantaine te beheren

### <a name="view-quarantined-email"></a>E-mail in quarantaine weergeven

1. Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.

2. Controleer of **Weergave in quarantaine** is ingesteld op de **standaardwaarde-e-mail**.

3. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):

   - **Ontvangen**<sup>\*</sup>

   - **Afzender**<sup>\*</sup>

   - **Onderwerp**<sup>\*</sup>

   - **Reden van quarantaine**<sup>\*</sup>

   - **Vrijgegeven?**<sup>\*</sup>

   - **Beleidstype**<sup>\*</sup>

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

     - **Beleid**: Het bericht voldeed aan de voorwaarden van een e-mailstroomregel (ook wel een transportregel genoemd).

     - **Bulk**

     - **Phishing**

     - **Malware**

     - **Spam**

     - **Hoog vertrouwen Phish**

   - **E-mailontvanger:** Alle gebruikers of alleen berichten die naar u worden verzonden. Eindgebruikers kunnen alleen berichten in quarantaine beheren die naar hen worden verzonden.

   Als u het filter wilt wissen, drukt u op **Wissen**. Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.

5. Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken. Jokertekens worden niet ondersteund. U kunt zoeken op een van de volgende waarden:

   - **Bericht-ID**: de wereldwijd unieke identificatie van het bericht.

     U hebt bijvoorbeeld [berichttracering](message-trace-scc.md) gebruikt om te zoeken naar een bericht dat naar een gebruiker in uw organisatie is verzonden en u bepaalt dat het bericht in quarantaine is geplaatst in plaats van geleverd. Zorg ervoor dat u de volledige waarde van de bericht-ID opneemt, die hoekbeugels () kan \<\> bevatten. Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .

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

- **Quarantainereden**: geeft aan of een bericht is geïdentificeerd als **Spam**, **Bulk**, **Phish**, overeenkomen met een mailflowregel **(Transportregel),** of is geïdentificeerd als malware **.**

- **Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.

- **Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.

- **Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.

- **Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.

### <a name="take-action-on-quarantined-email"></a>Actie ondernemen op e-mail in quarantaine

Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u moet doen met de berichten in het flyoutvenster **Details:**

- **Releasebericht**: Kies in het flyout-deelvenster dat wordt weergegeven de volgende opties:

  - **Berichten rapporteren aan Microsoft voor analyse:** dit is standaard geselecteerd en rapporteert het foutieve bericht in quarantaine aan Microsoft als een fout-positief. Als het bericht in quarantaine is geplaatst als spam, bulk, phishing of malware bevat, wordt het bericht ook gerapporteerd aan het Microsoft Spam Analysis Team. Afhankelijk van hun analyse kunnen de regels voor het hele spamfilter voor de hele service worden aangepast om het bericht door te laten.

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

- **Bericht verzenden**: Kies in het flyout-deelvenster dat wordt weergegeven de volgende opties:

  - **Objecttype**: **E-mail** (standaard), **URL**of **Bijlage**.

  - **Inzendingsvorm**: **netwerkbericht-id** (standaard, met de bijbehorende waarde in het vak **Netwerkbericht-id)** of **Bestand** (blader naar een lokaal .eml- of .msg-bestand). Als u **Bestand** selecteert en **vervolgens Netwerkbericht-id**selecteert, is de oorspronkelijke waarde verdwenen.

  - **Geadresseerden**: typ bij leasen van één oorspronkelijke ontvanger van het bericht of klik op **Alles selecteren** om alle ontvangers te identificeren. U ook op **Alles selecteren** klikken en vervolgens selectief afzonderlijke ontvangers verwijderen.

  - **Reden voor indiening**: **Had niet geblokkeerd mogen worden** (standaard) of geblokkeerd moeten **worden.**

  Klik op **Verzenden**als u klaar bent.

Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Actie ondernemen op meerdere e-mailberichten in quarantaine

Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:

- **Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.

  > [!NOTE]
  > Houd rekening met het volgende scenario: john@gmail.com stuurt een bericht naar faith@contoso.com en john@subsidiary.contoso.com. Gmail bifurcates dit bericht in twee exemplaren die beide zijn doorgestuurd naar quarantaine als phishing in Microsoft. Een beheerder geeft beide berichten vrij om te admin@contoso.com. Het eerste vrijgegeven bericht dat het beheerderspostvak bereikt, wordt bezorgd. Het tweede vrijgegeven bericht wordt geïdentificeerd als dubbele levering en wordt overgeslagen. Bericht worden geïdentificeerd als duplicaten als ze dezelfde bericht-ID en ontvangen tijd hebben.

- **Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.

Klik op **Sluiten** wanneer u gereed bent.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Alleen ATP: gebruik het Security & Compliance Center om in quarantaine geplaatste bestanden te beheren

> [!NOTE]
> De procedures voor in quarantaine geplaatste bestanden in deze sectie zijn alleen beschikbaar voor ATP-abonnement 1- en Plan 2-abonnees.

In organisaties met ATP kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.

### <a name="view-quarantined-files"></a>Bestanden in quarantaine weergeven

1. Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.

2. **Weergave wijzigen die in quarantaine is geplaatst** in de standaardwaardebestanden . **files** U sorteren op een veld door op een beschikbare kolomkop te klikken.

3. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. De standaardkolommen zijn gemarkeerd met een sterretje ( <sup>\*</sup> ):

   - **Gebruiker**<sup>\*</sup>

   - **Locatie**<sup>\*</sup>

   - **Bestandsnaam**<sup>\*</sup>

   - **BESTANDS-URL**<sup>\*</sup>

   - **Bestandsgrootte**<sup>\*</sup>

   - **Vervalt op**<sup>\*</sup>

   - **Vrijgegeven?**<sup>\*</sup>

   - **Gedetecteerd door**

   - **Gewijzigd op tijd**

4. Klik op **Filter** om de resultaten te filteren. De beschikbare filters zijn:

   - **Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:

     - **Vandaag**

     - **Komende 2 dagen**

     - **Komende 7 dagen**

     - Een aangepast datum-tijdbereik.

   - **Ontvangen tijd**

   - **Quarantaine reden:** De enige beschikbare waarde is **Malware**.

Nadat u een specifiek in quarantaine geplaatst bestand hebt gevonden, selecteert u het bestand om er details over te bekijken en actie te ondernemen (bijvoorbeeld het bericht weergeven, vrijgeven, downloaden of verwijderen).

#### <a name="export-file-results"></a>Bestandsresultaten exporteren

1. Selecteer de bestanden waarin u geïnteresseerd bent en klik op **Resultaten exporteren**.

2. Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.

3. Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.

#### <a name="view-quarantined-file-details"></a>Bestandsgegevens in quarantaine weergeven

Wanneer u een bestand in de lijst selecteert, worden de volgende bestandsdetails weergegeven in het flyoutvenster **Details:**

- **Bestandsnaam**

- **BESTANDS-URL:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).

- **Schadelijke inhoud gedetecteerd op** De datum/tijd dat het bestand in quarantaine is geplaatst.

- **Verloopt**: de datum waarop het bestand uit quarantaine wordt verwijderd.

- **Gedetecteerd door**: ATP (Advanced Threat Protection) of Microsoft's anti-malware engine.

- **Vrijgegeven?**

- **Malwarenaam**

- **Document-id**: een unieke id voor het document.

- **Bestandsgrootte**: In kilobytes (KB).

- **Organisatie** De unieke ID van uw organisatie.

- **Laatst gewijzigd**

- **Gewijzigd door**: De gebruiker die het bestand voor het laatst heeft gewijzigd.

- **Secure Hash Algorithm 256-bits (SHA-256) waarde**: U deze hashwaarde gebruiken om het bestand te identificeren in andere reputatiewinkels of op andere locaties in uw omgeving.

### <a name="take-action-on-quarantined-files"></a>Actie ondernemen op in quarantaine geplaatste bestanden

Wanneer u een bestand in de lijst selecteert, u de volgende acties uitvoeren in het bestand in het flyoutvenster **Details:**

- **Bestanden vrijgeven**: Selecteer (standaard) of schakel **Rapportbestanden uit voor Analyse**en klik op Bestanden **vrijgeven**.

- **Bestand downloaden**

- **Bestand uit quarantaine verwijderen**

Als u de bestanden niet vrijlaat of verwijdert, worden ze verwijderd nadat de standaardretentieperiode voor quarantaine is verstreken.

#### <a name="actions-on-multiple-quarantined-files"></a>Acties op meerdere bestanden in quarantaine

Wanneer u meerdere bestanden in quarantaine in de lijst selecteert (maximaal 100), wordt het flyoutvenster **Bulkacties** weergegeven waar u de volgende acties uitvoeren:

- **Bestanden vrijgeven**

- **Bestanden verwijderen**: Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de bestanden onmiddellijk verwijderd.

1. Meld u aan en [ga naar het Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)met algemene beheerdersrechten (of de juiste rollen security & Compliance Center) in uw organisatie.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om berichten en bestanden in quarantaine te bekijken en te beheren

De cmdlets die u gebruikt om berichten en bestanden in quarantaine te bekijken en te beheren zijn:

- [Bericht in quarantaine verwijderen](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [In quarantaine exporterenMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [In quarantaine plaatsenMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Houd er rekening mee dat deze cmdlet alleen is voor berichten, niet voor malwarebestanden van ATP voor SharePoint Online, OneDrive voor Bedrijven of Teams.

- [Release-quarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
