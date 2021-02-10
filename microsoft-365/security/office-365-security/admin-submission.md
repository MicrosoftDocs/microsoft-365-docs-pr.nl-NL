---
title: Inzendingen door beheerders
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen in het beveiligings- en compliancecentrum van het beveiligings-&-compliancecentrum verdachte e-mailberichten, verdachte phishing-e-mailberichten, spam en andere mogelijk schadelijke berichten, URL's en bestanden voor scannen naar Microsoft verzenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7a822909c318cb336c179b299aa64cd71dcca4d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175869"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Inzending door beheerder gebruiken om verdachte spam, phish, URL's en bestanden bij Microsoft in te dienen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)


In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal Voorzendingen in het beveiligings- &-compliancecentrum gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft te verzenden om te scannen.

Wanneer u een e-mailbericht indient, krijgt u:

1. **Controle van e-mailverificatie:** Details over het al dan niet doorgegeven of mislukt van de e-mailverificatie toen deze werd geleverd.
2. **Beleidstreffers:** informatie over beleid dat inkomende e-mail in uw tenant mogelijk heeft toegestaan of geblokkeerd, waardoor onze servicefilters worden overschrijven.
3. **Nettoladingsreput/detonatie:** Onderzoek van eventuele URL's en bijlagen in het bericht.
4. **Cijferanalyse:** beoordeling door beoordelingsbeoordelingen om te controleren of berichten schadelijk zijn of niet.

> [!IMPORTANT]
> De nettoladings-/detonatie- en cijferanalyse worden niet in alle tenants uitgevoerd. Informatie wordt geblokkeerd voor het verlaten van de organisatie wanneer gegevens de tenantgrens niet mogen verlaten voor nalevingsdoeleinden.

Zie Berichten en bestanden rapporteren bij Microsoft voor andere manieren om e-mailberichten, URL's en bijlagen bij [Microsoft in te dienen.](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **inzendingspagina wilt** gaan, gebruikt u <https://protection.office.com/reportsubmission> .

- Als u berichten en bestanden wilt verzenden bij Microsoft, moet u lid zijn van een van de volgende rollengroepen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).

  - **Organisatiebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

    Houd er rekening mee dat lidmaatschap van deze rollengroep is vereist om [gebruikersinzendingen voor](#view-user-submissions-to-the-custom-mailbox) het aangepaste postvak weer te geven, zoals verder wordt beschreven in dit artikel.

- Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen [verzenden bij Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Verdachte inhoud rapporteren aan Microsoft

1. Ga in het & compliancecentrum naar  Inzendingen voor \> **bedreigingsbeheer,** controleer of u zich op het tabblad **Admin-inzendingen** vindt en klik vervolgens op **Nieuwe inzending.**

2. Gebruik **de flyout** Nieuwe inzending die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.

### <a name="submit-a-questionable-email-to-microsoft"></a>Een twijfelachtig e-mailbericht naar Microsoft verzenden

1. Selecteer **E-mail in** de sectie **Objecttype.** Gebruik in **de sectie Indeling** voor inzending een van de volgende opties:

   - Netwerkbericht-id: dit is een GUID-waarde die beschikbaar is in de kop **X-MS-Exchange-Organization-Network-Message-Id** in het bericht of in de **kop X-MS-Office365-Filtering-Correlation-Id** in berichten in quarantaine.

   - **Bestand:** klik **op Bestand kiezen.** Zoek en selecteer het EML- of MSG-bestand in het dialoogvenster dat wordt geopend en klik op **Openen.**

   > [!NOTE]
   > Beheerders met Defender voor Office 365-abonnement 1 of Abonnement 2 kunnen berichten verzenden die dertig dagen oud zijn. Andere beheerders kunnen slechts zeven dagen teruggaan.

2. Geef in **de sectie Ontvangers** een of meer geadresseerden op voor wie u een beleidscontrole wilt uitvoeren. Met de beleidscontrole wordt bepaald of scannen van e-mail is overgeslagen vanwege het beleid van de gebruiker of organisatie.

3. Selecteer een **van de volgende opties in** de sectie Reden voor inzending:

   - **Was niet geblokkeerd**

   - **Zou geblokkeerd moeten zijn:** **Spam,** **Phishing** of **Malware selecteren.** Als u het niet zeker weet, moet u dit goed doen.

4. Klik op de knop Verzenden wanneer u **klaar** bent.

   ![Voorbeeld van URL-inzending](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Een verdachte URL naar Microsoft verzenden

1. Selecteer URL **in de** sectie **Objecttype.** Voer in het vak dat wordt weergegeven de volledige URL in `https://www.fabrikam.com/marketing.html` (bijvoorbeeld).

2. Selecteer een **van de volgende opties in** de sectie Reden voor inzending:

   - **Was niet geblokkeerd**

   - **Zou geblokkeerd moeten zijn:** Selecteer **Phishing** of **Malware.**

3. Klik op de knop Verzenden wanneer u **klaar** bent.

   ![Voorbeeld van e-mailinzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Een verdacht bestand indienen bij Microsoft

1. Selecteer Bijlage **in de** sectie **Objecttype.**

2. Klik **op Bestand kiezen.** Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en klik op **Openen.**

3. Selecteer een **van de volgende opties in** de sectie Reden voor inzending:

   - **Was niet geblokkeerd**

   - **Zou geblokkeerd moeten zijn:** **Malware** is de enige optie en wordt automatisch geselecteerd.

4. Klik op de knop Verzenden wanneer u **klaar** bent.

   ![Voorbeeld van bijlageinzending](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Inzendingen van beheerders weergeven

Ga in het & compliancecentrum naar  Inzendingen voor \> **bedreigingsbeheer,** controleer of u zich op het tabblad **Admin-inzendingen** vindt en klik vervolgens op **Nieuwe inzending.**

Boven aan de pagina kunt u een begindatum en einddatum invoeren en **(standaard)** u kunt filteren op Indiening-id (een GUID-waarde die is toegewezen aan elke inzending) door een waarde in het vak in te voeren en op de knop Vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken. U kunt meerdere waarden invoeren, gescheiden door komma's.

Als u de filtercriteria wilt wijzigen, klikt u op **de knop Id** van indiening en kiest u een van de volgende waarden:

- **Afzender**
- **Onderwerp/URL/bestandsnaam**
- **Ingediend door**
- **Type indiening**
- **Status**

![Filteropties voor inzendingen door beheerders](../../media/admin-submission-email-filter-options.png)

Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel.** Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.

Onder de grafiek ziet u drie tabbladen: **E-mail** (standaard), **URL** en **Bijlage.**

### <a name="view-admin-email-submissions"></a>E-mailinzendingen van beheerders weergeven

Klik op het **tabblad E-mail.**

U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Datum**
- **Indienings-id:** een GUID-waarde die is toegewezen aan elke inzending.
- **Ingediend door**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **AFZENDER-IP**<sup>\*</sup>
- **Type indiening**
- **Bezorgings reden**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

#### <a name="admin-submission-rescan-details"></a>Rescandetails voor inzending door beheerder

Berichten die worden ingediend in beheerdersinzendingen, worden opnieuw gescand en de resultaten worden weergegeven in de details van de flyout:

- Als er een fout is geweest in de e-mailverificatie van de afzender op het moment van bezorging.
- Informatie over beleidstreffers die invloed kunnen hebben op of overschrijven van het bericht.
- De huidige detonatieresultaten om te zien of de URL's of bestanden in het bericht schadelijk zijn of niet.
- Feedback van cijferaars.

Als een overschrijven is gevonden, zou het opnieuw scannen binnen enkele minuten moeten zijn voltooid. Als er geen probleem is met e-mailverificatie of bezorging niet is beïnvloed door een overschrijven, kan de feedback van cijferaars tot een dag duren.

### <a name="view-admin-url-submissions"></a>Url-inzendingen voor beheerders weergeven

Klik op het **tabblad URL.**

U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Datum**
- **Inzendings-id**
- **Ingediend door**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Type indiening**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

### <a name="view-admin-attachment-submissions"></a>Inzendingen voor beheerdersbijlagen weergeven

Klik op **het tabblad** Bijlagen.

U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Datum**
- **Inzendings-id**
- **Ingediend door**<sup>\*</sup>
- **Bestandsnaam**<sup>\*</sup>
- **Type indiening**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

## <a name="view-user-submissions-to-microsoft"></a>Gebruikersinzendingen voor Microsoft weergeven

Als u de invoegversie Bericht rapporteren, [de invoegversie](enable-the-report-message-add-in.md) [Voor](enable-the-report-phish-add-in.md)phishing melden hebt geïmplementeerd of als mensen de [ingebouwde](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapportage in de webversie van Outlook gebruiken, kunt u zien wat gebruikers melden op het tabblad **Gebruikersinzendingen.**

1. Ga in het & Compliancecentrum naar **Inzendingen voor** \> **risicobeheer.**

2. Selecteer het **tabblad Gebruikersinzendingen** en klik op **Nieuwe inzending.**

U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Ingediend op**
- **Ingediend door**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **AFZENDER-IP**<sup>\*</sup>
- **Type indiening**

<sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

Boven aan de pagina kunt u een begindatum en einddatum invoeren en (standaard) filteren op afzender door een waarde in het vak in te voeren en op de knop Vernieuwen te  ![ ](../../media/scc-quarantine-refresh.png) klikken. U kunt meerdere waarden invoeren, gescheiden door komma's.

Als u de filtercriteria wilt wijzigen, klikt u op **de knop Afzender** en kiest u een van de volgende waarden:

- **Afzenderdomein**
- **Onderwerp**
- **Ingediend door**
- **Type indiening**
- **AFZENDER-IP**

![Filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel.** Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Gebruikersinzendingen voor het aangepaste postvak weergeven

**Als** u een [aangepast](user-submission.md) postvak hebt geconfigureerd voor het ontvangen van door de gebruiker gerapporteerde berichten, kunt u berichten bekijken en verzenden die zijn bezorgd in het postvak van de rapportage.

1. Ga in het & Compliancecentrum naar **Inzendingen voor** \> **risicobeheer.**

2. Selecteer het **tabblad Aangepast postvak.**

U kunt op de **knop Kolomopties** onderaan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Ingediend op**
- **Ingediend door**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **AFZENDER-IP**<sup>\*</sup>
- **Type indiening**

Boven aan de pagina kunt u een begindatum en einddatum invoeren  en u kunt filteren op Ingediend door een waarde in het vak in te voeren en op de knop Vernieuwen ![ te ](../../media/scc-quarantine-refresh.png) klikken. U kunt meerdere waarden invoeren, gescheiden door komma's.

Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel.** Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.

## <a name="undo-user-submissions"></a>Gebruikersinzendingen ongedaan maken

Wanneer een gebruiker een verdachte e-mail naar het aangepaste postvak indient, hebben de gebruiker en beheerder geen optie om de inzending ongedaan te maken. Als de gebruiker de e-mail wil herstellen, kan deze worden hersteld in de mappen Verwijderde items of Ongewenste e-mail.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Berichten naar Microsoft verzenden vanuit het aangepaste postvak

Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft verzenden voor analyse. Hiermee wordt een gebruikersinzending op effectieve wijze verplaatst naar een inzending door een beheerder.

Selecteer op **het tabblad** Aangepast postvak een  bericht in de lijst, klik op de knop Actie en maak een van de volgende selecties:

- **Rapport opschoont**
- **Phishing melden**
- **Malware melden**
- **Spam melden**

![Opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
