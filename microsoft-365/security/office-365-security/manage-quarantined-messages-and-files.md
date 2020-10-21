---
title: Berichten en bestanden in quarantaine beheren als beheerder
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Beheerders kunnen informatie lezen over het weergeven en beheren van quarantaine berichten voor alle gebruikers in Exchange Online Protection (EOP). Beheerders in organisaties met Office 365 Advanced Threat Protection (Office 365 ATP) kunnen ook quarantaine bestanden beheren in SharePoint Online, OneDrive voor bedrijven en Microsoft teams.
ms.openlocfilehash: 65cf0a116dbed3dce93db8e34fa96d6ab68a9c9e
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626165"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Berichten en bestanden in quarantaine beheren als EOP-beheerder

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst. Zie voor meer informatie [Gequarantinee e-mailberichten in EOP](quarantine-email-messages.md).

Beheerders kunnen alle typen quarantaine berichten voor alle gebruikers weergeven, vrijgeven en verwijderen. Alleen beheerders kunnen berichten beheren die zijn gequarantined met malware, phishing van hoge betrouwbaarheid of als gevolg van de regels voor de e-mail stroom (ook wel transport regels genoemd). Beheerders kunnen ook fout-positieven rapporteren aan Microsoft.

Beheerders in organisaties met Office 365 Advance Threat Protection (Office 365 ATP) kunnen ook in quarantaine geplaatste bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams weergeven, downloaden en verwijderen.

U kunt berichten in quarantaine weergeven en beheren in het beveiligings & nalevings centrum of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder postvakken van Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://protection.office.com> om het Beveiligings- en compliancecentrum te openen. Ga naar <https://protection.office.com/quarantine> als u de quarantaine-pagina direct wilt openen.

- Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) als u verbinding wilt maken met standalone EOP PowerShell.

- U moet machtigingen zijn toegewezen voordat u de quarantaine als een beheerder kunt beheren. De machtigingen worden beheerd op basis van de rol van **Quarantine** in het compliance-& Beveiligingscentrum. Deze functie wordt standaard toegewezen aan **Organisatiebeheer** (globale beheerders), **Quarantine beheerder**en **Beveiligingsbeheerders** van rollen in het nalevings centrum voor beveiligings &. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

- Berichten in quarantaine worden gedurende een standaardperiode bewaard voordat ze automatisch worden verwijderd:

  - Berichten die worden gequarantined door Antispambeleid (spam, phishing en bulk-e-mail): 30 dagen. Dit is de standaard-en maximumwaarde. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md)als u deze waarde wilt configureren.

  - Berichten die schadelijke software bevatten: 15 dagen.

  Wanneer een bericht verloopt over quarantaine, kunt u dit niet herstellen.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>De beveiligings & voor compliance gebruiken voor het beheren van e-mailberichten in quarantaine

### <a name="view-quarantined-email"></a>Gequarantinede e-mail weergeven

1. Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.

2. Controleer of **weergave in quarantaine** is ingesteld op de standaardwaarde **-e-mail**.

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

   - **Ontvangen op**: voer een **begindatum** en**einddatum** in.

   - **Reden van quarantaine**:
     - **Beleid**: het bericht voldoet aan de voorwaarden van een e-mail stroom regel (ook wel een transportregel genoemd).
     - **Bulk**
     - **Phishing**: de spamfilter verdict was **phishing-e-mail** of Anti Phishing Protection het bericht ([spoof-instellingen](set-up-anti-phishing-policies.md#spoof-settings) of [imitatie bescherming](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)).
     - **Malware**
     - **Spam**
     - **Hoge betrouwbaarheid van phishing**

   - **Beleidstype**: berichten filteren op beleidstype:
     - **Anti malwarebeleid**
     - **Beleid voor veilige bijlagen**
     - **Beleid tegen phishing**
     - **Filter beleid met gehoste inhoud** (Antispambeleid)
     - **Transport regel**

   - **E-mail ontvanger**: alle gebruikers of alleen berichten die naar u zijn verzonden. Eindgebruikers kunnen alleen quarantaine berichten beheren die ze hebben verzonden.

   Als u het filter wilt wissen, drukt u op **Wissen**. Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.

5. Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken. Jokertekens worden niet ondersteund. U kunt zoeken op een van de volgende waarden:

   - **Bericht-ID**: de wereldwijd unieke identificatie van het bericht.

     U gebruikt bijvoorbeeld de [bericht tracering](message-trace-scc.md) om te zoeken naar een bericht dat is verzonden naar een gebruiker in uw organisatie en u hebt vastgesteld dat het bericht is in quarantaine geplaatst in plaats van afgeleverd. Zorg ervoor dat u de volledige waarde voor de bericht-ID opneemt, waaronder punthaken ( \<\> ). Voor `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` Beeld:

   - **E-mailadres afzender**: een enkel e-mailadres van een afzender.

   - **Beleidsnaam**: gebruik de volledige Beleidsnaam van het bericht. De zoekopdracht is niet hoofdlettergevoelig.

   - **E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.

   - **Onderwerp**: gebruik het volledige onderwerp van het bericht. De zoekopdracht is niet hoofdlettergevoelig.
  
   - **Beleidsnaam**: de naam van het beleid dat verantwoordelijk is voor het quarantining van het bericht.

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

- **Reden voor quarantaine**: geeft aan of een bericht als **spam**, **bulksgewijs**, **phishing**of in overeenstemming met een e-mail stroom regel (**transport regel**) is geïdentificeerd, of dat is geïdentificeerd als **malware**.

- **Aantal geadresseerden**

- **Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.

- **Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.

- **Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.

- **Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.

### <a name="take-action-on-quarantined-email"></a>Actie ondernemen op e-mail in quarantaine

Wanneer u een bericht hebt geselecteerd, kunt u in het vervolgmenu **Details** verschillende opties opgeven voor wat u wilt doen met de berichten:

- **Release bericht**: Kies in het deelvenster flyout dat wordt weergegeven de volgende opties:

  - **Meld u aan bij Microsoft for Analysis**: deze optie is standaard geselecteerd en rapporten geeft het abusievelijk gequarantinee bericht aan Microsoft als een onwaar positief. Als het bericht is gequarantined als spam, bulksgewijs, phishing of malware bevat, wordt het bericht ook gerapporteerd aan het Microsoft spam Analysis-Team. Afhankelijk van de analyse kunnen de regels voor spamfilters van het serviceniveau worden aangepast om het bericht toe te staan.

  - Kies een van de volgende opties:
    - **Berichten uitbrengen voor alle geadresseerden**
    - **Berichten vrijgeven aan specifieke geadresseerden**
    - **Berichten uitbrengen aan andere personen**

  Klik op **Berichten vrijgeven** wanneer u gereed bent.

  Opmerkingen over het vrijgeven van berichten:

  - U kunt een bericht niet meer dan één keer vrijgeven voor dezelfde geadresseerde.
  - Alleen geadresseerden die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële geadresseerden.

- **Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken. Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien). Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:

- **Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:

  - **Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.
  - **Tekstweergave**: toont het bericht in gewone tekst.

- **Uit quarantaine verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht direct verwijderd zonder dat het naar de oorspronkelijke geadresseerden wordt verzonden.

- **Bericht downloaden**: selecteer in het deelvenster dat wordt weergegeven **Ik begrijp de risico’s van het downloaden van dit bericht** om een lokale kopie van het bericht op te slaan in .eml-indeling.

- **Bericht verzenden**: Kies de volgende opties in het deelvenster flyout dat wordt weergegeven:

  - **Object type**: **e-mail** (standaard), **URL**of **bijlage**.

  - **Indeling voor indienen**: **netwerkbericht-id** (standaard met de overeenkomstige waarde in het vak **netwerkbericht-id** ) of **bestand** (Blader naar een Local. eml-of. msg-bestand). Als u **bestand** selecteert en vervolgens **netwerkbericht-id**selecteert, is de aanvankelijke waarde verdwenen.

  - **Geadresseerden**: Typ een originele geadresseerde van het bericht, of klik op **Alles selecteren** om alle geadresseerden te identificeren. U kunt ook op **de knop Alles selecteren** klikken en vervolgens selectief afzonderlijke geadresseerden verwijderen.

  - **Reden voor indiening**: **mag niet zijn geblokkeerd** (standaardinstelling) of **moet zijn geblokkeerd**.

  Als u klaar bent, klikt u op **verzenden**.

Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Actie ondernemen op meerdere e-mailberichten in quarantaine

Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:

- **Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.

  > [!NOTE]
  > Kijk eens naar het volgende scenario: john@gmail.com verzendt een bericht naar faith@contoso.com en john@subsidiary.contoso.com. Gmail bifurcates dit bericht in twee kopieën die beide worden gerouteerd naar Quarantine als phishing in Microsoft. Een beheerder geeft beide berichten vrij op admin@contoso.com. Het eerste uitgebrachte bericht waarin het postvak van de beheerder is bereikt, wordt bezorgd. Het tweede uitgebrachte bericht wordt geïdentificeerd als duplicaten ontvangst en wordt overgeslagen. Berichten worden geïdentificeerd als duplicaten als ze dezelfde bericht-ID hebben en tijd hebben ontvangen.

- **Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.

Klik op **Sluiten** wanneer u gereed bent.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Alleen ATP: gebruik het beveiligings & voor compliance voor het beheren van bestanden die in quarantaine zijn geplaatst

> [!NOTE]
> De procedures voor in deze sectie geplaatste bestanden zijn alleen beschikbaar voor de abonnement 1 en abonnement 2.

In organisaties met een ATP kunnen beheerders in SharePoint Online, OneDrive voor bedrijven en Microsoft teams in quarantaine geplaatste bestanden beheren. Zie [ATP voor SharePoint, OneDrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md)inschakelen om beveiliging voor deze bestanden in te schakelen.

### <a name="view-quarantined-files"></a>Bestanden met quarantaine weergeven

1. Ga in het beveiligings- en compliancecentrum naar **Risicobeheer** \> **Bekijken** \> **Quarantaine**.

2. Wijzig de **weergave in quarantaine** voor de Value **files**. U kunt op een veld sorteren door te klikken op een beschikbare kolomkop.

3. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. De standaardkolommen zijn gemarkeerd met een sterretje ( <sup>\*</sup> ):

   - **Aanmeldings**<sup>\*</sup>
   - **Locatie**<sup>\*</sup>
   - **Bestandsnaam**<sup>\*</sup>
   - **Bestands-URL**<sup>\*</sup>
   - **Bestandsgrootte**<sup>\*</sup>
   - **Vervalt op**<sup>\*</sup>
   - **Vrijgegeven?**<sup>\*</sup>
   - **Gedetecteerd door**
   - **Gewijzigd door de tijd**

4. Klik op **Filter** om de resultaten te filteren. De beschikbare filters zijn:

   - **Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:
     - **Vandaag**
     - **Komende 2 dagen**
     - **Komende 7 dagen**
     - Een aangepast datum/tijdbereik.
   - **Tijdstip van de ontvangst**
   - **Reden voor quarantaine**: de enige beschikbare waarde is **malware**.
   - **Beleidstype**

Wanneer u een specifiek in quarantaine geplaatste bestand hebt gevonden, selecteert u het bestand om de details ervan weer te geven, en kunt u actie ondernemen (u kunt het bericht bijvoorbeeld weergeven, vrijgeven, downloaden of verwijderen).

#### <a name="export-file-results"></a>Bestandsresultaten exporteren

1. Selecteer de bestanden waarin u bent geïnteresseerd en klik op **resultaten exporteren**.

2. Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.

3. Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.

#### <a name="view-quarantined-file-details"></a>Details van bestand met quarantaine weergeven

Wanneer u een bestand in de lijst selecteert, worden de volgende details van het bestand weergegeven in het deelvenster **Details** :

- **Bestandsnaam**
- **Bestands-URL**: URL waarmee de locatie van het bestand wordt gedefinieerd (bijvoorbeeld in SharePoint Online).
- **Schadelijke inhoud gedetecteerd op** De datum/tijd waarop het bestand is gequarantined.
- **Verloopt**op: de datum waarop het bestand in quarantaine wordt verwijderd.
- **Gedetecteerd door**: ATP (Advanced Threat Protection) of de anti malware-engine van Microsoft.
- **Vrijgegeven?**
- **Naam van malware**
- **Document-id**: een unieke id voor het document.
- **Bestandsgrootte**: in kilobytes (KB).
- **Organisatie** Unieke ID van uw organisatie.
- **Laatst gewijzigd**
- **Gewijzigd door**: de gebruiker die het bestand het laatst heeft gewijzigd.
- **Secure Hash Algorithm 256-bit (SHA-256)**: u kunt deze hash-waarde gebruiken om het bestand te identificeren in andere reputatie winkels of op andere locaties in uw omgeving.

### <a name="take-action-on-quarantined-files"></a>Actie ondernemen op bestanden in quarantaine

Wanneer u een bestand in de lijst selecteert, kunt u de volgende acties voor het bestand in het deelvenster met **Details** van de vervolgkeuzelijst opnemen:

- **Release bestanden**: Selecteer (standaardinstelling) of hef de selectie **van de bestanden voor Microsoft**op en klik vervolgens op **bestanden vrijgeven**.
- **Bestand downloaden**
- **Het bestand verwijderen uit Quarantine**

Als u de bestanden niet uitgeeft of verwijdert, worden deze verwijderd nadat de standaard bewaarperiode voor quarantaine is verlopen.

#### <a name="actions-on-multiple-quarantined-files"></a>Acties op meerdere gequarantinee bestanden

Wanneer u in de lijst meerdere quarantaine bestanden selecteert (maximaal 100), wordt het menu met de opdracht **bulk acties** weergegeven, waarin u de volgende acties kunt uitvoeren:

- **Bestanden vrijgeven**
- **Bestanden verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die verschijnt, worden de bestanden direct verwijderd.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>PowerShell van Exchange Online of zelfstandige EOP PowerShell gebruiken om quarantaine berichten en-bestanden weer te geven en te beheren

De cmdlets die u gebruikt voor het weergeven en beheren van berichten en bestanden in quarantaine, zijn:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Voorbeeld: QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): deze cmdlet is alleen voor berichten, geen malware-bestanden uit de ATP voor SharePoint Online, OneDrive voor bedrijven of teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
