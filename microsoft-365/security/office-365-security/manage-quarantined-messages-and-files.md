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
description: Beheerders kunnen leren hoe u berichten in quarantaine kunt weergeven en beheren voor alle gebruikers in Exchange Online Protection (EOP). Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen ook in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 59bdfdaddbc091467bfd2ccddc2c40377955fab3
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028989"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Berichten en bestanden in quarantaine beheren als EOP-beheerder

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst. Zie In quarantaine geplaatste [e-mailberichten in EOP](quarantine-email-messages.md)voor meer informatie.

Beheerders kunnen alle typen in quarantaine geplaatste berichten voor alle gebruikers weergeven, vrijgeven en verwijderen. Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware, phishing met veel vertrouwen of als gevolg van regels voor e-mailstroom (ook wel transportregels genoemd). Beheerders kunnen ook fout-positieven melden bij Microsoft.

Beheerders in organisaties met Microsoft Defender voor Office 365 kunnen ook in quarantaine geplaatste bestanden weergeven, downloaden en verwijderen in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.

U bekijkt en beheert in quarantaine geplaatste berichten in de Microsoft 365 Defender-portal of in PowerShell (Exchange Online PowerShell voor Microsoft 365-organisaties met postvakken in Exchange Online; zelfstandige EOP PowerShell voor organisaties zonder Exchange Online-postvakken).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Ga naar <https://security.microsoft.com> als je de Microsoft 365 Defender-portal wilt openen. Ga naar <https://security.microsoft.com/quarantine> als je de Quarantaine-pagina direct wilt openen.

- Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell. Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.

- U moet over toegewezen machtigingen beschikken in **Exchange Online** voordat u de procedures in dit artikel kunt uitvoeren:
  - Als u actie wilt ondernemen voor berichten in quarantaine voor alle gebruikers, moet u lid zijn van de rollengroepen Organisatiebeheer, **Beveiligingsbeheerder** of **Quarantainebeheerder.** <sup>\*</sup>
  - Voor alleen-lezen toegang tot in quarantaine geplaatste berichten voor alle gebruikers, moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**

  Zie [Machtigingen in Exchange Online](/exchange/permissions-exo/permissions-exo) voor meer informatie.

  **Opmerkingen**:

  - Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.
  - De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.
  - <sup>\*</sup>Leden van **de** rollengroep Quarantainebeheerder moeten ook lid zijn van de rollengroep **Hygiënebeheer** [in](/Exchange/permissions-exo/permissions-exo#role-groups) Exchange Online om quarantaineprocedures uit te voeren in Exchange Online PowerShell.

- Berichten in quarantaine worden bewaard voor een standaardperiode voordat ze automatisch worden verwijderd:
  - 30 dagen voor berichten die in quarantaine zijn geplaatst door antispambeleid (spam, phishing en bulk-e-mail). Dit is de standaardwaarde en de maximumwaarde. Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md)als u deze waarde wilt configureren (lager).
  - 15 dagen voor berichten die malware bevatten.
  - 15 dagen voor bestanden die in quarantaine zijn geplaatst door Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams in Defender voor Office 365.

  Wanneer een bericht verloopt vanuit quarantaine, kunt u het bericht niet herstellen.

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-email-messages"></a>De portal Microsoft 365 Defender in quarantaine geplaatste e-mailberichten beheren

### <a name="view-quarantined-email"></a>In quarantaine geplaatste e-mail weergeven

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Controleren** \> **Quarantine**.

2. Controleer op **de** pagina Quarantaine of **Weergave in quarantaine** is ingesteld op de standaardwaarde-e-mail. 

3. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. Standaardwaarden worden aangegeven met een sterretje (<sup>\*</sup>):

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

4. Klik op **Filter** om de resultaten te filteren. De beschikbare filters zijn:
   - **Vervaldatum**: filtert de berichten op de datum dat de quarantaineperiode vervalt:
     - **Vandaag**
     - **Komende 2 dagen**
     - **Komende 7 dagen**
     - **Aangepast**: voer een **begindatum** en **einddatum** in.
   - **Ontvangen op**: voer een **begindatum** en **einddatum** in.
   - **Reden van quarantaine**:
     - **Beleid:** Het bericht komt overeen met de voorwaarden van een e-mailstroomregel (ook wel een transportregel genoemd).
     - **Bulk**
     - **Phish:** De uitspraak van het spamfilter was Phishing-e-mail of anti-phishingbeveiliging die het bericht in quarantaine heeft geplaatst [(spoofinstellingen](set-up-anti-phishing-policies.md#spoof-settings) of [imitatiebeveiliging).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 
     - **Malware**
     - **Spam**
     - **Phish met hoog vertrouwen**
   - **Beleidstype**: berichten filteren op beleidstype:
     - **Anti-malwarebeleid**
     - **Safe Bijlagebeleid**
     - **Beleid tegen phishing**
     - **Beleid voor gehoste inhoudsfilters** (antispambeleid)
     - **Transportregel**
   - **E-mailontvanger:** Alle gebruikers of alleen berichten die naar u zijn verzonden. Eindgebruikers kunnen alleen in quarantaine geplaatste berichten beheren die naar hen zijn verzonden.

   Als u het filter wilt wissen, drukt u op **Wissen**. Als u het filterdeelvenster wilt verbergen, klikt u opnieuw op **Filter**.

5. Gebruik **Resultaten sorteren op** (standaard de knop **Bericht-ID**) en een bijbehorende waarde om naar specifieke berichten te zoeken. Jokertekens worden niet ondersteund. U kunt zoeken op een van de volgende waarden:
   - **Bericht-ID**: de wereldwijd unieke identificatie van het bericht.

     U hebt bijvoorbeeld [](message-trace-scc.md) berichtspoor gebruikt om te zoeken naar een bericht dat is verzonden naar een gebruiker in uw organisatie en u bepaalt dat het bericht in quarantaine is geplaatst in plaats van bezorgd. Zorg ervoor dat u de id-waarde voor het volledige bericht op moet nemen, waaronder hoekhaken ( \<\> ). Bijvoorbeeld: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .

   - **E-mailadres afzender**: een enkel e-mailadres van een afzender.
   - **Beleidsnaam**: gebruik de volledige Beleidsnaam van het bericht. De zoekopdracht is niet hoofdlettergevoelig.
   - **E-mailadres ontvanger**: een enkel e-mailadres van een ontvanger.
   - **Onderwerp**: gebruik het volledige onderwerp van het bericht. De zoekopdracht is niet hoofdlettergevoelig.
   - **Naam van** het beleid: de naam van het beleid dat verantwoordelijk was voor het kwaalveren van het bericht.

   Nadat u de zoekcriteria hebt opgegeven, klikt u op de ![Knop vernieuwen](../../media/scc-quarantine-refresh.png) **Vernieuwen** om de resultaten te filteren.

Nadat u een specifiek bericht in quarantaine hebt gevonden, selecteert u het bericht om de details te bekijken en actie te ondernemen (bijvoorbeeld bericht bekijken, vrijgeven, downloaden of verwijderen).

#### <a name="view-quarantined-message-details"></a>Gegevens van bericht in quarantaine bekijken

Wanneer u een e-mailbericht in de lijst selecteert, zijn de volgende berichtdetails beschikbaar in de details flyout die wordt weergegeven:

- **Bericht-ID**: de wereldwijd unieke identificatie van het bericht.
- **Adres afzender**
- **Ontvangen op**: de datum/tijd waarop het bericht is ontvangen.
- **Onderwerp**
- **Reden voor quarantaine:** geeft aan of een bericht is geïdentificeerd als **Spam**, **Bulk**, **Phish**, overeenkomend met een regel voor de e-mailstroom (**transportregel**) of is geïdentificeerd als **malware.**
- **Aantal geadresseerden**
- **Ontvangers**: als het bericht naar meerdere ontvangers is gestuurd, moet u klikken op **Preview bericht** of **Berichtkop bekijken** om de volledige lijst met ontvangers te zien.
- **Vervalt op**: de datum/tijd waarop het bericht automatisch en permanent wordt verwijderd uit quarantaine.
- **Vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht is vrijgegeven.
- **Nog niet vrijgegeven aan**: alle e-mailadressen (indien aanwezig) waaraan het bericht nog niet is vrijgegeven.

### <a name="take-action-on-quarantined-email"></a>Actie ondernemen op e-mail in quarantaine

Nadat u een bericht hebt geselecteerd, hebt u verschillende opties voor wat u moet doen met de berichten in de details flyout:

- **Releasebericht:** Kies de volgende opties in het flyout dat wordt weergegeven:
  - **Berichten rapporteren aan Microsoft voor analyse:** Dit is standaard geselecteerd en meldt het verkeerd in quarantaine geplaatste bericht aan Microsoft als een onwaar positief bericht. Als het bericht in quarantaine is geplaatst als spam, bulksgewijs, phishing of malware bevat, wordt het bericht ook gerapporteerd aan het Microsoft Spam Analysis Team. Afhankelijk van hun analyse kunnen de regels voor spamfilters voor de hele service worden aangepast om het bericht door te sturen.
  - Kies een van de volgende opties:
    - **Berichten vrijgeven voor alle geadresseerden**
    - **Berichten vrijgeven aan specifieke geadresseerden**
    - **Berichten vrijgeven aan andere personen:** houd er rekening mee dat het vrijgeven van malwareberichten aan andere personen dan oorspronkelijke geadresseerden niet wordt ondersteund.

  Klik op **Berichten vrijgeven** wanneer u gereed bent.

  Notities over het vrijgeven van berichten:

  - U kunt een bericht niet meer dan één keer vrijgeven aan dezelfde geadresseerde.
  - Alleen geadresseerden die het bericht niet hebben ontvangen, worden weergegeven in de lijst met potentiële geadresseerden.

- **Berichtkop bekijken**: kies deze koppeling om de tekst van de berichtkop te bekijken. Om de kopvelden en -waarden uitgebreid te analyseren, kopieert u de berichtkoptekst naar uw klembord en kies vervolgens **Microsoft-berichtkopanalyse** om naar de Verbindingsanalyse op afstand te gaan (klik met de rechtermuisknop en kies **In een nieuw tabblad openen** als u Microsoft 365 niet wilt verlaten om deze taak te voltooien). Plak de berichtkop in de pagina in de sectie Berichtkopanalyse en kies **Koppen analyseren**:
- **Voorbeeldbericht:** Kies een van de volgende opties in het flyout dat wordt weergegeven:
  - **Bronweergave**: toont de HTML-versie van het bericht met uitgeschakelde koppelingen.
  - **Tekstweergave**: toont het bericht in gewone tekst.
- **Uit quarantaine verwijderen:** nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, wordt het bericht onmiddellijk verwijderd zonder naar de oorspronkelijke geadresseerden te worden verzonden.
- **Bericht downloaden:** Selecteer in het flyout dat wordt weergegeven de optie Ik begrijp de risico's van het downloaden van dit bericht om een lokale kopie van het bericht op te slaan in .eml-indeling. 
- **Afzenders blokkeren**: voeg de afzender toe aan de lijst met geblokkeerde afzenders in uw postvak. Raadpleeg [Afzender van e-mail blokkeren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4) voor meer informatie.
- **Bericht verzenden:** Kies de volgende opties in het flyout dat wordt weergegeven:
  - **Objecttype:** **E-mail** (standaard), **URL** of **Bijlage**.
  - **Inzendingsindeling:** **Netwerkbericht-id** (standaard,  met de bijbehorende waarde in het vak Netwerkbericht-id) **of** Bestand (bladeren naar een lokaal .eml- of .msg-bestand). Als u Bestand **selecteert** en vervolgens **Netwerkbericht-id** selecteert, is de oorspronkelijke waarde verdwenen.
  - **Geadresseerden:** Typ bij lease één oorspronkelijke geadresseerde van het bericht of klik **op Alles selecteren** om alle geadresseerden te identificeren. U kunt ook op **Alles selecteren** klikken en afzonderlijke geadresseerden vervolgens selectief verwijderen.
  - **Reden voor indiening:** **Had niet moeten worden geblokkeerd** (standaard) of Had moeten worden **geblokkeerd.**

  Wanneer u klaar bent, klikt u op **Verzenden.**

Als u het bericht niet vrijgeeft of verwijdert, wordt het verwijderd nadat de standaard quarantaineperiode is verlopen.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Actie ondernemen op meerdere e-mailberichten in quarantaine

Wanneer u meerdere in quarantaine geplaatste berichten in de  lijst selecteert (maximaal 100), wordt het fly-out Bulkacties weergegeven waar u de volgende acties kunt uitvoeren:

- **Berichten vrijgeven**: de opties zijn dezelfde als wanneer u een enkel bericht vrijgeeft, behalve dat u **Berichten vrijgeven aan specifieke ontvangers** niet kunt selecteren. U kunt alleen **Bericht vrijgeven aan alle ontvangers** of **Berichten vrijgeven aan andere personen**.

  > [!NOTE]
  > Houd rekening met het volgende scenario: john@gmail.com stuurt een bericht naar faith@contoso.com en john@subsidiary.contoso.com. Gmail zet dit bericht op in twee exemplaren die beide naar quarantaine worden gerouteerd als phishing in Microsoft. Een beheerder geeft beide berichten vrij aan admin@contoso.com. Het eerste uitgebrachte bericht dat het postvak van de beheerder bereikt, wordt bezorgd. Het tweede uitgebrachte bericht wordt geïdentificeerd als dubbele bezorging en wordt overgeslagen. Berichten worden geïdentificeerd als duplicaten als ze dezelfde bericht-id en ontvangen tijd hebben.

- **Berichten verwijderen:** Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de berichten onmiddellijk verwijderd zonder naar de oorspronkelijke geadresseerden te worden verzonden.

Klik op **Sluiten** wanneer u gereed bent.

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365"></a>Gebruik de Microsoft 365 Defender portal voor het beheren van in quarantaine geplaatste bestanden in Defender voor Office 365
> [!NOTE]
> De procedures voor in quarantaine geplaatste bestanden in deze sectie zijn alleen beschikbaar voor Abonnees Office 365 Abonnement 1 en Abonnement 2.

In organisaties met Defender voor Office 365 kunnen beheerders in quarantaine geplaatste bestanden beheren in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams. Zie Safe Bijlagen inschakelen voor [SharePoint, OneDrive en Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)

### <a name="view-quarantined-files"></a>In quarantaine geplaatste bestanden weergeven

1. Ga in de Microsoft 365 Defender-portal naar **E-mail en samenwerking** \> **Controleren** \> **Quarantine**.


2. Op de **pagina Quarantaine** wijzigt u Weergave in **quarantaine in** de **waardebestanden.** U kunt sorteren op een veld door op een beschikbare kolomkop te klikken.

3. U kunt de resultaten sorteren door op een beschikbare kolomkop te klikken. Klik op **Kolommen wijzigen** om maximaal zeven kolommen te laten zien. De standaardkolommen zijn gemarkeerd met een sterretje ( <sup>\*</sup> ):
   - **Gebruiker**<sup>\*</sup>
   - **Locatie**<sup>\*</sup>
   - **Bestandsnaam**<sup>\*</sup>
   - **BestandS-URL**<sup>\*</sup>
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
   - **Ontvangen tijd**
   - **Reden voor quarantaine:** De enige beschikbare waarde is **Malware.**
   - **Beleidstype**

Nadat u een specifiek bestand in quarantaine hebt gevonden, selecteert u het bestand om de details ervan weer te geven en om actie te ondernemen (bijvoorbeeld het bericht weergeven, vrijgeven, downloaden of verwijderen).

#### <a name="view-quarantined-file-details"></a>In quarantaine geplaatste bestandsgegevens weergeven

Wanneer u een bestand in de lijst selecteert, zijn de volgende bestandsgegevens beschikbaar in de details flyout die wordt geopend:

- **Bestandsnaam**
- **BestandS-URL:** URL die de locatie van het bestand definieert (bijvoorbeeld in SharePoint Online).
- **Schadelijke inhoud gedetecteerd op** De datum/tijd waarop het bestand in quarantaine is geplaatst.
- **Verloopt:** De datum waarop het bestand uit quarantaine wordt verwijderd.
- **Gedetecteerd door**: Defender voor Office 365 of de anti-malware-engine van Microsoft.
- **Vrijgegeven?**
- **Malwarenaam**
- **Document-id:** een unieke id voor het document.
- **Bestandsgrootte:** in kilobytes (KB).
- **Organisatie** De unieke id van uw organisatie.
- **Laatst gewijzigd**
- **Gewijzigd door**: De gebruiker die het bestand het laatst heeft gewijzigd.
- **Secure Hash Algorithm 256-bits (SHA-256)** waarde: U kunt deze hashwaarde gebruiken om het bestand te identificeren in andere reputatiestores of op andere locaties in uw omgeving.

### <a name="take-action-on-quarantined-files"></a>Actie ondernemen voor in quarantaine geplaatste bestanden

Wanneer u een bestand in de lijst selecteert, kunt u de volgende acties uitvoeren in het bestand in de details flyout:

- **Releasebestanden:** Selecteer (standaard) of deselecteer **Rapportbestanden** naar Microsoft voor analyse en klik vervolgens op **Bestanden vrijgeven.**
- **Downloadbestand**
- **Bestand uit quarantaine verwijderen**

Als u de bestanden niet los laat of verwijdert, worden deze verwijderd nadat de standaard bewaarperiode voor quarantaine is verlopen.

#### <a name="actions-on-multiple-quarantined-files"></a>Acties voor meerdere in quarantaine geplaatste bestanden

Wanneer u meerdere in quarantaine geplaatste bestanden in de  lijst selecteert (maximaal 100), wordt het fly-out Bulkacties weergegeven waar u de volgende acties kunt uitvoeren:

- **Bestanden vrijgeven**
- **Bestanden verwijderen:** Nadat u op **Ja** hebt geklikt in de waarschuwing die wordt weergegeven, worden de bestanden onmiddellijk verwijderd.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Gebruik Exchange Online PowerShell of zelfstandige EOP PowerShell om in quarantaine geplaatste berichten en bestanden weer te geven en te beheren

De cmdlets die u gebruikt voor het weergeven en beheren van berichten en bestanden in quarantaine zijn:

- [Delete-QuarantineMessage](/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)deze cmdlet is alleen voor berichten, niet voor bestanden in quarantaine van Safe Bijlagen voor SharePoint, OneDrive en Microsoft Teams.

- [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
