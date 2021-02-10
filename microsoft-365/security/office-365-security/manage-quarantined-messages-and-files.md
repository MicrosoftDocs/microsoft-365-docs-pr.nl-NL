---
title: Berichten en bestanden in quarantaine beheren als beheerder
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Beheerders kunnen informatie krijgen over het weergeven en beheren van in quarantaine geplaatste berichten voor alle gebruikers in Exchange Online Protection (EOP). Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen ook in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a91f53f8efe4fa6944f0debff472da87b7f17e0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167489"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Berichten en bestanden in quarantaine beheren als EOP-beheerder

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst. Zie In quarantaine [geplaatste e-mailberichten in EOP voor meer informatie.](quarantine-email-messages.md)

Beheerders kunnen alle typen in quarantaine geplaatste berichten voor alle gebruikers weergeven, vrijgeven en verwijderen. Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, zeer vertrouwelijk phishing of als gevolg van regels voor de e-mailstroom (ook wel transportregels genoemd). Beheerders kunnen ook fout-positieven rapporteren aan Microsoft.

Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen in quarantaine geplaatste bestanden ook weergeven, downloaden en verwijderen in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.

U bekijkt en beheert berichten in quarantaine in het beveiligings- &-compliancecentrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen. Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- Je moet beschikken over toegewezen machtigingen in het Beveiligings- en compliancecentrum voor het uitvoeren van de procedures in dit onderwerp:
  - Als u acties wilt uitvoeren op berichten in quarantaine voor alle gebruikers, moet u lid zijn van de rollengroepen Organisatiebeheer, Beveiligingsbeheerder of  <sup>\*</sup> Quarantainebeheerder.
  - Voor alleen-lezen toegang tot berichten in quarantaine voor alle gebruikers  moet u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.
  - <sup>\*</sup> Leden van de **rollengroep Quarantainebeheerder** moeten ook lid zijn van de rollengroep **Systeembeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) om quarantaineprocedures te kunnen uitvoeren in Exchange Online PowerShell.

- In quarantaine geplaatste berichten worden een standaardperiode bewaard voordat ze automatisch worden verwijderd:
  - 30 dagen voor berichten die in quarantaine worden geplaatst door antispambeleid (spam, phishing en bulk-e-mail). Dit is de standaardwaarde en de maximumwaarde. Zie Antispambeleid configureren als u deze waarde (lager) [wilt configureren.](configure-your-spam-filter-policies.md)
  - 15 dagen voor berichten die malware bevatten.
  - 15 dagen voor bestanden die in quarantaine worden geplaatst door veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams in Defender voor Office 365.

  Wanneer een bericht in quarantaine is verlopen, kunt u het niet herstellen.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Het beveiligings- & voor het beheren van e-mailberichten die in quarantaine zijn geplaatst

### <a name="view-quarantined-email"></a>In quarantaine geplaatste e-mail weergeven

1. Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.

2. Controleer of **In quarantaine weergeven** is ingesteld op het standaardwaarde-e-mailbericht. 

3. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):

   - **Ontvangen**<sup>\*</sup>
   - **Afzender**<sup>\*</sup>
   - **Onderwerp**<sup>\*</sup>
   - **Reden van quarantaine**<sup>\*</sup>
   - **Vrijgegeven?**<sup>\*</sup>
   - **Beleidstype**<sup>\*</sup>
   - **Vervalt op**
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

   - **Ontvangen op**: voer een **begindatum** en **einddatum** in.

   - **Reden van quarantaine**:
     - **Beleid:** het bericht komt overeen met de voorwaarden van een e-mailstroomregel (ook wel transportregel genoemd).
     - **Bulk**
     - **Phish:** het spamfilter was Phishing-e-mail of anti-phishingbeveiliging in quarantaine geplaatst (instellingen voor [spoofing](set-up-anti-phishing-policies.md#spoof-settings) of [imitatiebeveiliging).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 
     - **Malware**
     - **Spam**
     - **Phish met hoog vertrouwen**

   - **Beleidstype**: berichten filteren op beleidstype:
     - **Anti-malwarebeleid**
     - **Beleid voor veilige bijlagen**
     - **Beleid tegen phishing**
     - **Beleid voor gehoste inhoudsfilters** (antispambeleid)
     - **Transportregel**

   - **E-mailontvanger:** Alle gebruikers of alleen berichten die naar u zijn verzonden. Eindgebruikers kunnen alleen in quarantaine geplaatste berichten beheren die naar hen worden verzonden.

   Als u het filter wilt wissen, drukt u op **Wissen**. Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.

5. Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken. Jokertekens worden niet ondersteund. U kunt zoeken op een van de volgende waarden:

   - **Bericht-ID**: de wereldwijd unieke identificatie van het bericht.

     U hebt bericht [](message-trace-scc.md) traceren bijvoorbeeld gebruikt om te zoeken naar een bericht dat is verzonden naar een gebruiker in uw organisatie en u hebt vastgesteld dat het bericht in quarantaine is geplaatst in plaats van is bezorgd. Zorg ervoor dat u de volledige waarde van de bericht-id, die hoekhaken ( ) kan bevatten, \<\> bevat. Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .

   - **E-mailadres afzender**: een enkel e-mailadres van een afzender.

   - **Beleidsnaam**: gebruik de volledige Beleidsnaam van het bericht. De zoekopdracht is niet hoofdlettergevoelig.

   - **E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.

   - **Onderwerp**: gebruik het volledige onderwerp van het bericht. De zoekopdracht is niet hoofdlettergevoelig.

   - **Beleidsnaam:** de naam van het beleid dat verantwoordelijk was voor het quarantining van het bericht.

   Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.

Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).

#### <a name="view-quarantined-message-details"></a>Gegevens van bericht in quarantaine bekijken

Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:

- **Bericht-ID**: de wereldwijd unieke identificatie van het bericht.

- **Adres afzender**

- **Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.

- **Onderwerp**

- **Reden in** quarantaine: geeft aan of een bericht is geïdentificeerd als **Spam,** **Bulk,** **Phish,** aan een regel voor de e-mailstroom **(transportregel)** of is geïdentificeerd als **malware.**

- **Aantal geadresseerden**

- **Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.

- **Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.

- **Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.

- **Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.

### <a name="take-action-on-quarantined-email"></a>Actie ondernemen op e-mail in quarantaine

Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u wilt doen met de berichten in het deelvenster **Details:**

- **Releasebericht:** kies de volgende opties in het flyoutvenster dat wordt weergegeven:

  - **Rapporteer berichten aan Microsoft** voor analyse: Dit is standaard geselecteerd en meldt het bericht dat verkeerd in quarantaine is geplaatst bij Microsoft als fout-positief. Als het bericht in quarantaine is geplaatst als spam, bulkmail, phishing of malware bevat, wordt het bericht ook gerapporteerd aan het Microsoft-team voor spamanalyse. Afhankelijk van de analyse kunnen de regels voor het filteren van spam voor de hele service zo worden aangepast dat het bericht wordt doorgestuurd.

  - Kies een van de volgende opties:
    - **Berichten vrijgeven aan alle geadresseerden**
    - **Berichten vrijgeven aan specifieke geadresseerden**
    - **Berichten vrijgeven aan andere personen:** het vrijgeven van malware aan andere personen dan oorspronkelijke geadresseerden wordt niet ondersteund.

  Klik op **Berichten vrijgeven** wanneer u gereed bent.

  Opmerkingen over het vrijgeven van berichten:

  - U kunt een bericht maar één keer vrijgeven aan dezelfde geadresseerde.
  - Alleen geadresseerden die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële geadresseerden.

- **Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken. Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien). Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:

- **Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:

  - **Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.
  - **Tekstweergave**: toont het bericht in gewone tekst.

- **Verwijderen uit quarantaine:** nadat u **in** de waarschuwing die wordt weergegeven op Ja hebt geklikt, wordt het bericht onmiddellijk verwijderd zonder dat het naar de oorspronkelijke geadresseerden wordt verzonden.

- **Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.

- **Bericht verzenden:** kies de volgende opties in het flyoutvenster dat wordt weergegeven:

  - **Objecttype:** **E-mail** (standaard), **URL** of **Bijlage.**

  - **Inzendingsindeling:** **Netwerkbericht-id** (standaard met  de bijbehorende waarde in het vak Netwerkbericht-id) of **Bestand** (blader naar een lokaal EML- of MSG-bestand). Als u Bestand **selecteert en vervolgens** Netwerkbericht-id selecteert, is de oorspronkelijke waarde verdwenen. 

  - **Geadresseerden:** typ een oorspronkelijke geadresseerde van het bericht bij leasen of klik op Alles **selecteren** om alle geadresseerden te identificeren. U kunt ook op **Alles selecteren** klikken en afzonderlijke geadresseerden vervolgens selectief verwijderen.

  - **Reden voor het indienen:** **het bericht had niet moeten zijn geblokkeerd** (standaard) of moet zijn **geblokkeerd.**

  Klik op Verzenden wanneer u **klaar bent.**

Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Actie ondernemen op meerdere e-mailberichten in quarantaine

Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:

- **Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.

  > [!NOTE]
  > Houd rekening met het volgende scenario: john@gmail.com verzendt een bericht naar faith@contoso.com en john@subsidiary.contoso.com. Gmail zet dit bericht op in twee kopieën die als phishing in Microsoft in quarantaine worden geplaatst. Een beheerder publiceert beide berichten naar admin@contoso.com. Het eerste uitgebrachte bericht dat het postvak van de beheerder bereikt, wordt bezorgd. Het tweede uitgebrachte bericht wordt geïdentificeerd als dubbele bezorging en wordt overgeslagen. Berichten worden als duplicaten geïdentificeerd als ze dezelfde bericht-id en tijd van ontvangst hebben.

- **Berichten verwijderen:** nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd zonder dat ze worden verzonden naar de oorspronkelijke geadresseerden.

Klik op **Sluiten** wanneer u gereed bent.

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Alleen Microsoft Defender voor Office 365: het beveiligings- & voor het beheren van in quarantaine geplaatste bestanden

> [!NOTE]
> De procedures voor bestanden in quarantaine in deze sectie zijn alleen beschikbaar voor abonnees van Microsoft Defender voor Office 365 Abonnement 1 en Abonnement 2.

In organisaties met Defender voor Office 365 kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams. Zie Veilige bijlagen inschakelen voor [SharePoint, OneDrive](turn-on-atp-for-spo-odb-and-teams.md)en Microsoft Teams voor meer informatie over het inschakelen van beveiliging voor deze bestanden.

### <a name="view-quarantined-files"></a>Bestanden in quarantaine weergeven

1. Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.

2. Weergave **in quarantaine wijzigen** in de **waardebestanden.** U kunt sorteren op een veld door te klikken op een beschikbare kolomkop.

3. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. De standaardkolommen zijn gemarkeerd met een sterretje ( <sup>\*</sup> ):

   - **Gebruiker**<sup>\*</sup>
   - **Locatie**<sup>\*</sup>
   - **Bestandsnaam**<sup>\*</sup>
   - **Bestands-URL**<sup>\*</sup>
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
     - Een aangepast datum-/tijdbereik.
   - **Tijd ontvangen**
   - **Reden in quarantaine:** de enige beschikbare waarde is **Malware.**
   - **Beleidstype**

Nadat u een specifiek in quarantaine geplaatst bestand hebt gevonden, selecteert u het bestand om de details ervan weer te geven en er actie op te ondernemen (bijvoorbeeld om het bericht te bekijken, los te laten, te downloaden of te verwijderen).

#### <a name="view-quarantined-file-details"></a>Bestandsgegevens in quarantaine weergeven

Wanneer u een bestand in de lijst selecteert, worden de volgende bestandsgegevens weergegeven in het flyoutvenster **Details:**

- **Bestandsnaam**
- **Bestands-URL:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).
- **Schadelijke inhoud gedetecteerd op** De datum/tijd waarop het bestand in quarantaine is geplaatst.
- **Verloopt:** de datum waarop het bestand in quarantaine wordt verwijderd.
- **Gedetecteerd door:** Defender voor Office 365 of de antimalware-engine van Microsoft.
- **Vrijgegeven?**
- **Malwarenaam**
- **Document-id:** een unieke id voor het document.
- **Bestandsgrootte:** in kilobytes (KB).
- **Organisatie** De unieke id van uw organisatie.
- **Laatst gewijzigd**
- **Gewijzigd door:** de gebruiker die het bestand het laatst heeft gewijzigd.
- **Secure Hash-algoritme 256-bits (SHA-256)-waarde:** U kunt deze hashwaarde gebruiken om het bestand te identificeren in andere reputatieopslag of op andere locaties in uw omgeving.

### <a name="take-action-on-quarantined-files"></a>Actie ondernemen voor bestanden in quarantaine

Wanneer u een bestand in de lijst selecteert, kunt u de volgende acties uitvoeren op het bestand in het deelvenster **Details:**

- **Releasebestanden:** selecteer (standaard) of deselecteer **Rapportbestanden** voor analyse bij Microsoft en klik op **Bestanden vrijgeven.**
- **Bestand downloaden**
- **Bestand uit quarantaine verwijderen**

Als u de bestanden niet los laat of verwijdert, worden ze verwijderd nadat de standaardbewaringsperiode voor quarantaine is verstreken.

#### <a name="actions-on-multiple-quarantined-files"></a>Acties voor meerdere bestanden in quarantaine

Wanneer u meerdere in quarantaine geplaatste bestanden in de  lijst selecteert (maximaal 100), wordt het flyoutvenster Bulkacties weergegeven waarin u de volgende acties kunt uitvoeren:

- **Releasebestanden**
- **Bestanden verwijderen:** nadat u in de waarschuwing **die** wordt weergegeven op Ja hebt geklikt, worden de bestanden onmiddellijk verwijderd.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Exchange Online PowerShell of een zelfstandige EOP PowerShell gebruiken om in quarantaine geplaatste berichten en bestanden weer te geven en te beheren

De cmdlets die u gebruikt voor het weergeven en beheren van berichten en bestanden in quarantaine zijn:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)deze cmdlet is alleen voor berichten, niet voor malwarebestanden van veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
