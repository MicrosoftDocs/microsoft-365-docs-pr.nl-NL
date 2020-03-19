---
title: Berichten en bestanden in quarantaine beheren als beheerder in Office 365
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
description: Beheerders kunnen alle typen berichten in quarantaine voor alle gebruikers bekijken, vrijgeven en verwijderen. Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met een hoog vertrouwen of als gevolg van regels voor de stroom (transportregels).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857071"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>Berichten en bestanden in quarantaine beheren als beheerder in Office 365

Quarantaine bevat mogelijk gevaarlijke of ongewenste berichten in Office 365-organisaties met postvakken in Exchange Online- of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken. Zie [Quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.

Beheerders kunnen alle typen berichten in quarantaine voor alle gebruikers bekijken, vrijgeven en verwijderen. Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met een hoog vertrouwen of als gevolg van regels voor de mailstroom (ook wel transportregels genoemd). Beheerders kunnen ook valse positieven melden aan Microsoft.

Beheerders in organisaties met Office 365 Advance Threat Protection (ATP) kunnen ook in quarantaine geplaatste bestanden bekijken, downloaden en verwijderen in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.

U bekijkt en beheert berichten in quarantaine in het Security & Compliance Center of in PowerShell (Exchange Online PowerShell voor Office 365-klanten; Exchange Online Protection PowerShell voor zelfstandige EOP-klanten).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Als u het Office 365 Security <https://protection.office.com>& Compliance Center wilt openen, gaat u naar . Als u de quarantainepagina <https://protection.office.com/quarantine>rechtstreeks wilt openen, gaat u naar .

- Zie Verbinding maken met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)als u verbinding wilt maken met Exchange Online PowerShell. Zie Verbinding maken met [PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)voor de beveiliging van Exchange Online.

- U moet machtigingen toegewezen krijgen voordat u de quarantaine als beheerder beheren. De machtigingen worden beheerd door de **quarantainerol** in het Security & Compliance Center. Deze rol wordt standaard toegewezen aan de rolgroepen **Organisatiebeheer** (Globale beheerders), **Quarantainebeheerder**en **Beveiligingsbeheerder** in het Security & Compliance Center. Zie [Machtigingen in het Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie.

- Berichten in quarantaine worden standaard bewaard voordat ze automatisch worden verwijderd:

  - Berichten in quarantaine geplaatst door antispambeleid (spam, phishing en bulke-mail): 30 dagen. Dit is de standaard waarde en maximale waarde. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)als u deze waarde wilt configureren.

  - Berichten die in quarantaine worden geplaatst door regels voor e-mailstroom (de regelactie is Het bericht verzenden **naar de gehoste quarantaine):** 30 dagen. Je deze waarde niet wijzigen.

  - Berichten die malware bevatten: 15 dagen.

  Wanneer een bericht uit quarantaine verloopt, u het niet herstellen.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Het Security & Compliance Center gebruiken om e-mailberichten in quarantaine te beheren

### <a name="view-quarantined-email"></a>In quarantaine geplaatste e-mail weergeven

1. Ga in het Security and Compliance Center naar **Threat Management** \> **Review** \> **Quarantine**.

2. Controleer of **Weergave in quarantaine** is ingesteld op **e-mail**met standaardwaarde .

3. U de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen weer te geven. De standaardwaarden zijn gemarkeerd met<sup>\*</sup>een sterretje ( ):

   - **Ontvangen**<sup>\*</sup>

   - **Afzender**<sup>\*</sup>

   - **Onderwerp**<sup>\*</sup>

   - **Quarantaine reden**<sup>\*</sup>

   - **Vrijgegeven?**<sup>\*</sup>

   - **Beleidstype**<sup>\*</sup>

   - **Verloopt**<sup>\*</sup>

   - **Ontvanger**

   - **Bericht-id**

   - **Beleidsnaam**

   - **Grootte**

   - **Richting**

   Wanneer u klaar bent, klikt u op **Opslaan**of klikt u op **Instellen op standaard**.

4. Als u de resultaten wilt filteren, klikt u op **Filter**. De beschikbare filters zijn:

   - **Verlooptijd**: Filter berichten op het moment dat ze verlopen vanuit quarantaine:

     - **Vandaag**

     - **Komende 2 dagen**

     - **Komende 7 dagen**

     - **Aangepast:** voer een **begindatum** en **einddatum**in .

   - **Ontvangen tijd**: Voer een **begindatum** en **einddatum**in .

   - **Quarantaine reden**:

     - **Beleid**: Het bericht kwam overeen met de voorwaarden van een e-mailstroomregel (ook wel een transportregel genoemd).

     - **Bulk**

     - **Phish**

     - **Malware**

     - **Spam**

     - **Hoog vertrouwen Phish**

   - **E-mailontvanger:** alle gebruikers of alleen berichten die naar u zijn verzonden. Eindgebruikers kunnen alleen berichten in quarantaine beheren die naar hen worden verzonden.

   Als u het filter wilt wissen, klikt u op **Wissen**. Als u de filterflyout wilt verbergen, klikt u nogmaals op **Filter.**

5. **Gebruik Sorteerresultaten op** (standaard de knop **Bericht-id)** en een bijbehorende waarde om specifieke berichten te vinden. Wildcards worden niet ondersteund. U zoeken op de volgende waarden:

   - **Bericht-id:** de wereldwijd unieke id van het bericht.

        U hebt bijvoorbeeld [berichttracering](message-trace-scc.md) gebruikt om te zoeken naar een bericht dat naar een gebruiker in uw organisatie is verzonden en u vaststelt dat het bericht in quarantaine is geplaatst in plaats van bezorgd. Zorg ervoor dat u de volledige waarde van de\<\>bericht-id opneemt, waaronder hoekhaakjes ( ). Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Afzender e-mailadres:** Het e-mailadres van één afzender.

   - **E-mailadres van**de ontvanger: het e-mailadres van één ontvanger.

   - **Onderwerp**: Gebruik het hele onderwerp van het bericht. De zoekopdracht is niet hoofdlettergevoelig.

   Nadat u de zoekcriteria hebt ![ingevoerd, klikt u op Knop](../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.

Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om details hierover weer te geven en u er actie op ondernemen (bijvoorbeeld het bericht bekijken, vrijgeven, downloaden of verwijderen).

#### <a name="export-message-results"></a>Berichtresultaten exporteren

1. Selecteer de berichten waarin u geïnteresseerd bent en klik op **Resultaten exporteren**.

2. Klik op **Ja** in het bevestigingsbericht waarin u wordt gewaarschuwd het browservenster open te houden.

3. Wanneer uw export klaar is, u de downloadlocatie voor het CSV-bestand benoemen en kiezen.

#### <a name="view-quarantined-message-details"></a>Berichtgegevens in quarantaine weergeven

Wanneer u een e-mailbericht in de lijst selecteert, worden de volgende berichtgegevens weergegeven in het flyout-venster **Details:**

- **Bericht-id:** de wereldwijd unieke id voor het bericht.

- **Afzenderadres**

- **Ontvangen**: De datum/tijd waarop het bericht is ontvangen.

- **Onderwerp**

- **Quarantaine reden**: Geeft aan of een bericht is geïdentificeerd als **Spam**, **Bulk**, **Phish**, overeen met een e-mailstroom regel **(Transport regel),** of werd geïdentificeerd als **malware**.

- **Ontvangers:** als het bericht meerdere geadresseerden bevat, moet u op **Bericht voorbeeld** of **berichtkop weergeven** klikken om de volledige lijst met geadresseerden weer te geven.

- **Verloopt:** De datum/tijd waarop het bericht automatisch en permanent uit quarantaine wordt verwijderd.

- **Vrijgegeven aan**: Alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.

- **Nog niet vrijgegeven aan**: Alle e-mailadressen (indien aanwezig) waarop het bericht nog niet is vrijgegeven.

### <a name="take-action-on-quarantined-email"></a>Actie ondernemen op e-mail in quarantaine

Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u moet doen met de berichten in het flyout-venster **Details:**

- **Bericht vrijgeven:** kies in het flyoutdeelvenster dat wordt weergegeven de volgende opties:

  - **Berichten rapporteren aan Microsoft voor analyse**: dit is standaard geselecteerd en rapporteert het ten onrechte geplaatste bericht aan Microsoft als een vals-positief. Als het bericht in quarantaine is geplaatst als spam, bulk, phishing of malware bevat, wordt het bericht ook gerapporteerd aan het Microsoft Spam Analysis Team. Afhankelijk van hun analyse kunnen de regels voor spamfilter voor de hele service worden aangepast om het bericht door te laten.

  - Kies een van de volgende opties:

    - **Berichten vrijgeven aan alle ontvangers**

    - **Berichten vrijgeven aan specifieke ontvangers**

    - **Berichten vrijgeven aan andere mensen**

  Klik op **Berichten vrijgeven**als u klaar bent.

  Opmerkingen over het vrijgeven van berichten:

  - U een bericht niet meerdere dan één keer vrijgeven aan dezelfde ontvanger.

  - Alleen ontvangers die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële ontvangers.

- **Berichtkoptekst weergeven:** kies deze koppeling om de tekst van de berichtkoptekst te bekijken. Als u de koptekstvelden en -waarden in de diepte wilt analyseren, kopieert u de tekst van de koptekst van het bericht naar uw klembord en kiest u **Vervolgens Microsoft Message Header Analyzer** om naar de Externe verbindingsanalyse te gaan (klik met de rechtermuisknop en kies Openen op een nieuw **tabblad** als u Office 365 niet wilt verlaten om deze taak te voltooien). Plak de berichtkoptekst op de pagina in de sectie Message Header Analyzer en kies **Kopteksten analyseren:**

- **Voorbeeldbericht:** Kies in het flyoutdeelvenster dat wordt weergegeven een van de volgende opties:

  - **Bronweergave**: Toont de HTML-versie van de berichttekst met alle koppelingen uitgeschakeld.
  
  - **Tekstweergave**: Toont de berichttekst in platte tekst.

- **Verwijderen uit quarantaine**: Nadat u op **Ja** in de waarschuwing die wordt weergegeven, hebt geklikt, wordt het bericht onmiddellijk verwijderd zonder dat het naar de oorspronkelijke geadresseerden is verzonden.

- **Downloadbericht**: Selecteer in het flyoutvenster dat wordt weergegeven **de risico's van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.

- **Bericht verzenden:** kies in het flyoutdeelvenster dat wordt weergegeven de volgende opties:

  - **Objecttype**: **E-mail** (standaard), **URL**of **bijlage**.

  - **Inzendingsindeling**: **Netwerkbericht-id** (standaard, met de bijbehorende waarde in het vak **Netwerkbericht-id)** of **Bestand** (blader naar een lokaal .eml- of .msg-bestand). Houd er rekening mee dat als u **Bestand** selecteert en vervolgens **Netwerkbericht-id**selecteert, de oorspronkelijke waarde is verdwenen.

  - **Geadresseerden**: Typ bij lease één oorspronkelijke ontvanger van het bericht of klik op **Alles selecteren** om alle geadresseerden te identificeren. U ook op **Alles selecteren** klikken en vervolgens selectief afzonderlijke ontvangers verwijderen.

  - **Reden voor indiening**: **Had niet geblokkeerd moeten zijn** (standaard) of had geblokkeerd moeten **worden.**

  Als u klaar bent, klikt u op **Verzenden**.

Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaardbewaarringsperiode voor quarantaine is verstreken.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Actie ondernemen op meerdere e-mailberichten in quarantaine

Wanneer u meerdere berichten in quarantaine selecteert in de lijst (maximaal 100), wordt het flyout-venster **Bulkacties** weergegeven waar u de volgende acties uitvoeren:

- **Berichten vrijgeven:** de opties zijn hetzelfde als wanneer u één bericht uitbrengt, behalve dat u Berichten vrijgeven **aan specifieke ontvangers**niet selecteren; u alleen **Bericht vrijgeven aan alle ontvangers** selecteren of Berichten vrijgeven aan andere **mensen.**

- **Berichten verwijderen:** Nadat u op **Ja** in de waarschuwing die wordt weergegeven, hebt geklikt, wordt het bericht onmiddellijk verwijderd zonder naar de oorspronkelijke geadresseerden te worden verzonden.

Als u klaar bent, klikt u op **Sluiten**.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Alleen ATP: gebruik het Security & Compliance Center om in quarantaine geplaatste bestanden te beheren

> [!NOTE]
> De procedures voor in quarantaine geplaatste bestanden in deze sectie zijn alleen beschikbaar voor ATP-abonnement 1- en Plan 2-abonnees.

In organisaties met ATP kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.

### <a name="view-quarantined-files"></a>In quarantaine geplaatste bestanden weergeven

1. Ga in het Security and Compliance Center naar **Threat Management** \> **Review** \> **Quarantine**.

2. **Weergave in quarantaine** wijzigen in de standaardwaardebestanden . **files** U sorteren op een veld door op een beschikbare kolomkop te klikken.

3. U de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen weer te geven. De standaardkolommen zijn gemarkeerd met<sup>\*</sup>een sterretje ( ):

   - **Gebruiker**<sup>\*</sup>

   - **Locatie**<sup>\*</sup>

   - **Bestandsnaam**<sup>\*</sup>

   - **Bestands-URL**<sup>\*</sup>

   - **Bestandsgrootte**<sup>\*</sup>

   - **Verloopt**<sup>\*</sup>

   - **Vrijgegeven?**<sup>\*</sup>

   - **Gedetecteerd door**

   - **Gewijzigd op tijd**

4. Als u de resultaten wilt filteren, klikt u op **Filter**. De beschikbare filters zijn:

   - **Verlooptijd**: Filter berichten op het moment dat ze verlopen vanuit quarantaine:

     - **Vandaag**

     - **Komende 2 dagen**

     - **Komende 7 dagen**

     - Een aangepast datum-/tijdsbereik.

   - **Ontvangen tijd**

   - **Quarantaine reden:** De enige beschikbare waarde is **Malware**.

Nadat u een specifiek bestand in quarantaine hebt gevonden, selecteert u het bestand om details hierover weer te geven en u er actie op ondernemen (bijvoorbeeld het bericht bekijken, vrijgeven, downloaden of verwijderen).

#### <a name="export-file-results"></a>Bestandsresultaten exporteren

1. Selecteer de bestanden waarin u geïnteresseerd bent en klik op **Resultaten exporteren**.

2. Klik op **Ja** in het bevestigingsbericht waarin u wordt gewaarschuwd het browservenster open te houden.

3. Wanneer uw export klaar is, u de downloadlocatie voor het CSV-bestand benoemen en kiezen.

#### <a name="view-quarantined-file-details"></a>In quarantaine geplaatste bestandsgegevens weergeven

Wanneer u een bestand in de lijst selecteert, worden de volgende bestandsgegevens weergegeven in het flyout-venster **Details:**

- **Bestandsnaam**

- **Bestands-URL:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).

- **Schadelijke inhoud gedetecteerd op** De datum/tijd dat het bestand in quarantaine is geplaatst.

- **Verloopt:** de datum waarop het bestand uit quarantaine wordt verwijderd.

- **Gedetecteerd door**: ATP (Advanced Threat Protection) of Microsoft's anti-malware engine.

- **Vrijgegeven?**

- **Malwarenaam**

- **Document-ID:** een unieke id voor het document.

- **Bestandsgrootte**: In kilobytes (KB).

- **Organisatie** De unieke ID van uw organisatie.

- **Laatst gewijzigd**

- **Gewijzigd door**: De gebruiker die het bestand het laatst heeft gewijzigd.

- **Secure Hash Algorithm 256-bit (SHA-256) waarde**: U deze hashwaarde gebruiken om het bestand te identificeren in andere reputatiewinkels of op andere locaties in uw omgeving.

### <a name="take-action-on-quarantined-files"></a>Actie ondernemen op bestanden in quarantaine

Wanneer u een bestand in de lijst selecteert, u de volgende acties uitvoeren in het bestand in het flyout-venster **Details:**

- **Bestanden vrijgeven:** Selecteer (standaard) of selecteer **Rapportbestanden aan Microsoft voor analyse**en klik vervolgens op Bestanden **vrijgeven**.

- **Downloadbestand**

- **Bestand uit quarantaine verwijderen**

Als u de bestanden niet vrijgeeft of verwijdert, worden ze verwijderd nadat de standaardbewaarringsperiode voor quarantaine is verstreken.

#### <a name="actions-on-multiple-quarantined-files"></a>Acties op meerdere bestanden in quarantaine

Wanneer u meerdere in quarantaine geplaatste bestanden in de lijst selecteert (maximaal 100), wordt het flyout-venster **Bulkacties** weergegeven waar u de volgende acties uitvoeren:

- **Bestanden vrijgeven**

- **Bestanden verwijderen:** Nadat u op **Ja** in de waarschuwing die wordt weergegeven, hebt geklikt, worden de bestanden onmiddellijk verwijderd.

Als u klaar bent, klikt u op **Sluiten**.

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell gebruiken om berichten en bestanden in quarantaine te bekijken en te beheren

De cmdlets die u gebruikt om berichten en bestanden in quarantaine te bekijken en te beheren zijn:

- [Bericht verwijderen in quarantaine](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Bericht exporteren-quarantaine](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Bericht in quarantaine](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage)Houd er rekening mee dat deze cmdlet alleen voor berichten is, niet voor malwarebestanden van ATP voor SharePoint Online, OneDrive voor Bedrijven of Teams.

- [Bericht in de release-quarantaine](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
