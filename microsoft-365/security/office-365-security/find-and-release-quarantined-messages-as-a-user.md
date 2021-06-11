---
title: Berichten in quarantaine zoeken en vrijgeven als gebruiker
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gebruikers kunnen meer informatie krijgen over het weergeven en beheren van berichten in quarantaine in Exchange Online Protection (EOP) die aan hun hadden moeten worden afgeleverd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 60b319b81362b9d88afcd734021db227969b04d0
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877870"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>Berichten in quarantaine zoeken en vrijgeven als gebruiker in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst. Zie [Quarantaine in EOP](quarantine-email-messages.md) voor meer informatie.

Als ontvanger van een in quarantaine geplaatst bericht wordt in de volgende tabel beschreven wat u als gewone gebruiker met het bericht kunt doen:

<br>

****

|Reden van quarantaine|Weergeven|Vrijgeven|Verwijderen|
|---|:---:|:---:|:---:|
|Bulk|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Spam|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|![Vinkje](../../media/checkmark.png)|
|Phishing (geen hoge phishingwaarschijnlijkheid)|![Vinkje](../../media/checkmark.png)||![Vinkje](../../media/checkmark.png)|
|

U kunt uw in quarantaine geplaatste berichten weergeven en beheren in de Microsoft 365 Defender-portal of (als een beheerder dit heeft ingesteld) in [spammeldingen voor eindgebruikers](use-spam-notifications-to-release-and-report-quarantined-messages.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://security.microsoft.com> als u de Microsoft 365 Defender-portal wilt openen. Ga naar <https://security.microsoft.com/quarantine> als u de quarantaine-pagina direct wilt openen.

- Beheerders kunnen instellen hoelang berichten in quarantaine blijven voordat ze permanent worden verwijderd in het antispambeleid. Berichten waarvan de quarantaine is verlopen, kunnen niet meer worden hersteld. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

- Beheerders kunnen ook [Spammeldingen voor eindgebruikers inschakelen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in antispambeleid. Gebruikers kunnen in quarantaine geplaatste ongewenste berichten rechtstreeks vanuit deze meldingen vrijgeven. Gebruikers kunnen in quarantaine geplaatste phishingberichten (niet phishingberichten van hoge waarschijnlijkheid) rechtstreeks vanuit deze meldingen controleren. Zie [Spammeldingen voor eindgebruikers in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md) voor meer informatie.

- Berichten die in quarantaine zijn geplaatst voor phishing van hoge waarschijnlijkheid, malware of door e-mailstroomregels (ook wel transportregels genoemd), zijn alleen beschikbaar voor beheerders en zijn niet zichtbaar voor gebruikers. Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).

- U kunt een bericht slechts eenmaal vrijgeven en melden als fout-positief (geen ongewenste e-mail).

## <a name="view-your-quarantined-messages"></a>Uw berichten in quarantaine bekijken

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Beoordeling** \> **Quarantine**.

2. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):

   - **Ontvangen**<sup>\*</sup>
   - **Afzender**<sup>\*</sup>
   - **Onderwerp**<sup>\*</sup>
   - **Reden van quarantaine**<sup>\*</sup>
   - **Vrijgegeven?**<sup>\*</sup>
   - **Beleidstype**<sup>\*</sup>
   - **Vervalt op**<sup>\*</sup>
   - **Ontvanger**
   - **Bericht-ID**
   - **Beleidsnaam**
   - **Grootte**
   - **Richting**

   Klik op **Opslaan** of op **Instellen op standaard** wanneer u gereed bent.

3. Klik op **Filter** om de resultaten te filteren. De beschikbare filters zijn:

   - **Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:
     - **Vandaag**
     - **Komende 2 dagen**
     - **Komende 7 dagen**
     - **Aangepast**: voer een **begindatum** en **einddatum** in.

   - **Ontvangen op**: voer een **begindatum** en **einddatum** in.

   - **Reden van quarantaine**:
     - **Bulk**
     - **Spam**
     - **Phishing**

   - **Beleidstype**: berichten filteren op beleidstype:
     - **Anti-malwarebeleid**
     - **Beleid voor veilige bijlagen** (Defender voor Office 365)
     - **Beleid tegen phishing**
     - **Beleid voor gehoste inhoudsfilters** (antispambeleid)
     - **Transportregel**

     <sup>\*</sup>

   Als u het filter wilt wissen, drukt u op **Wissen**. Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.

4. Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken. Jokertekens worden niet ondersteund. U kunt zoeken op een van de volgende waarden:

   - **Bericht-ID**: de wereldwijd unieke identificatie van het bericht. Als u een bericht selecteert in de lijst, verschijnt de waarde **Bericht-ID** in het deelvenster **Details** dat wordt weergegeven. Beheerders kunnen [berichttracering](message-trace-scc.md) gebruiken om naar berichten en de bijbehorende bericht-ID’s te zoeken.
   - **E-mailadres afzender**: een enkel e-mailadres van een afzender.
   - **Beleidsnaam**: gebruik de volledige Beleidsnaam van het bericht. De zoekopdracht is niet hoofdlettergevoelig.
   - **E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.
   - **Onderwerp**: gebruik het volledige onderwerp van het bericht. De zoekopdracht is niet hoofdlettergevoelig.

   Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.

Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).

### <a name="export-message-results"></a>Berichtresultaat exporteren

1. Selecteer de berichten waarin u bent geïnteresseerd en klik op **Resultaten exporteren**.

2. Klik op **Ja** in het bevestigingsbericht dat een waarschuwing weergeeft om het browservenster open te houden.

3. Wanneer uw export klaar is, kunt u de downloadlocatie voor het .csv-bestand benoemen en kiezen.

### <a name="view-quarantined-message-details"></a>Gegevens van bericht in quarantaine bekijken

Wanneer u een e-mailbericht selecteert in de lijst verschijnen de volgende berichtdetails in het deelvenster **Details**:

- **Bericht-ID**: de wereldwijd unieke identificatie van het bericht.
- **Adres afzender**
- **Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.
- **Onderwerp**
- **Reden van quarantaine**: wordt getoond als een bericht is geïdentificeerd als **Spam**, **Bulk** of **Phishing**.
- **Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.
- **Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.
- **Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.
- **Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.

### <a name="take-action-on-quarantined-email"></a>Actie ondernemen op e-mail in quarantaine

Nadat u een bericht selecteert, krijgt u in het deelvenster **Details** opties wat u met het bericht kunt doen:

- **Bericht vrijgeven**: kies in het deelvenster dat wordt weergegeven of u **Berichten wilt rapporteren aan Microsoft voor analyse**. Dit is standaard geselecteerd en rapporteert het bericht dat onterecht in quarantaine is geplaatst aan Microsoft als een fout-positief.

  Klik op **Berichten vrijgeven** wanneer u gereed bent.

- **Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken. Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien). Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:

- **Preview van bericht**: kies in het deelvenster dat wordt weergegeven een van de volgende opties:
  - **Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.
  - **Tekstweergave**: toont het bericht in gewone tekst.

- **Verwijderen uit quarantaine**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd.

- **Afzenders blokkeren**: voeg de afzender toe aan de lijst met geblokkeerde afzenders in uw postvak. Raadpleeg [Afzender van e-mail blokkeren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4) voor meer informatie.

Voeg de afzender toe aan de lijst met geblokkeerde afzenders in uw postvak. Raadpleeg [Afzender van e-mail blokkeren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4) voor meer informatie.

Klik op **Sluiten** wanneer u gereed bent.

Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Actie ondernemen op meerdere e-mailberichten in quarantaine

Wanneer u meerdere e-mailberichten in quarantaine selecteert (maximaal 100), verschijnt het deelvenster **Bulkopdrachten**, waar u de volgende acties kunt uitvoeren:

- **Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.
- **Berichten verwijderen**: nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd, zonder naar de originele ontvanger te worden verzonden.

Klik op **Sluiten** wanneer u gereed bent.
