---
title: Beheerdersinzendingen
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
description: Beheerders kunnen leren hoe ze de portal Inzendingen in het Microsoft 365-beveiligingscentrum kunnen gebruiken om verdachte e-mailberichten, vermoedelijke phishingmails, spam en andere potentieel schadelijke berichten, URL's en e-mailbijlagen bij Microsoft in te dienen voor het opnieuw controleren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878686"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)


In Microsoft 365 organisaties met postvakken in Exchange Online kunnen beheerders de portal Inzendingen in het beveiligings- &-compliancecentrum gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen voor scannen.

Wanneer u een e-mailbericht indient, krijgt u het volgende:

1. **Controle voor e-mailverificatie:** Details over het al dan niet geslaagd zijn van e-mailverificatie wanneer deze is bezorgd.
2. **Beleidstreffers:** Informatie over beleidsregels die de inkomende e-mail mogelijk hebben toegestaan of geblokkeerd in uw tenant, waardoor onze servicefilters worden overgenomen.
3. **Payload reputation/detonation**: Onderzoek van URL's en bijlagen in het bericht.
4. **Beoordelingsanalyse:** controleren door menselijke cijferaars om te controleren of berichten schadelijk zijn of niet.

> [!IMPORTANT]
> Payload reputation/detonation and grader analysis are not done in all tenants. Informatie wordt geblokkeerd om buiten de organisatie te gaan wanneer gegevens niet de tenantgrens moeten verlaten voor nalevingsdoeleinden.

Zie Berichten en bestanden rapporteren bij Microsoft voor andere manieren om e-mailberichten, URL's en bijlagen bij [Microsoft in te dienen.](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Microsoft 365 beveiligingscentrum op <https://security.microsoft.com/> . Als u rechtstreeks naar de pagina **Inzendingen wilt** gaan, gebruikt u <https://security.microsoft.com/reportsubmission> .

- Als u berichten en bestanden wilt verzenden naar Microsoft, moet u lid zijn van een van de volgende rollengroepen:

  - **Organisatiebeheer** of **Beveiligingslezer** in het [Microsoft 365 beveiligingscentrum.](permissions-microsoft-365-security-center.md)

  - **Organisatiebeheer** in [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)

    Houd er rekening mee dat lidmaatschap van deze rollengroep vereist is om gebruikersinzendingen in het aangepaste [postvak](#view-user-submissions-to-the-custom-mailbox) weer te geven, zoals verder wordt beschreven in dit artikel.

- Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen [bij Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Verdachte inhoud rapporteren aan Microsoft

1. Ga in [Microsoft 365 beveiligingscentrum](../defender/overview-security-center.md)naar **Inzendingen** en controleer of  u zich op het tabblad Ingediend voor analyse hebt en klik vervolgens op Verzenden bij **Microsoft voor controle.**

2. Gebruik de **flyout Verzenden bij Microsoft** voor controle die wordt weergegeven om het bericht, de URL of de e-mailbijlage in te dienen, zoals beschreven in de volgende secties.

### <a name="submit-a-questionable-email-to-microsoft"></a>Een twijfelachtige e-mail verzenden naar Microsoft

1. Selecteer **e-mail** in de sectie Selecteer het **inzendingstype.** Gebruik een van de volgende opties in de sectie **Netwerkbericht-id toevoegen** of het e-mailbestand uploaden:

   - **De** e-mailnetwerkbericht-id toevoegen: dit is een GUID-waarde die beschikbaar is in de koptekst **X-MS-Exchange-Organization-Network-Message-Id** in het bericht of in de **X-MS-Office365-Filtering-Correlation-Id-header** in in quarantaine geplaatste berichten.

   - **Upload het e-mailbestand:** Klik **op Bestanden bladeren.** Zoek en selecteer in het dialoogvenster dat wordt geopend het .eml- of .msg-bestand en klik vervolgens op **Openen.**

   > [!NOTE]
   > De mogelijkheid om berichten zo oud als 30 dagen in te dienen, is tijdelijk opgeschort voor Defender voor Office 365 klanten. Beheerders kunnen slechts 7 dagen teruggaan.

2. Geef in **de sectie Kies een geadresseerde** met een probleem de geadresseerde op tegen wie u een beleidscontrole wilt uitvoeren. Met de beleidscontrole wordt bepaald of het scannen per e-mail is overgeslagen vanwege gebruikers- of organisatiebeleid.

3. Selecteer in **de sectie Selecteer** een reden voor het indienen bij Microsoft een van de volgende opties:

   - **Had niet moeten worden geblokkeerd**

   - **Moet zijn geblokkeerd:** Selecteer **Spam,** **Phishing** of **Malware.** Als u het niet zeker weet, gebruikt u uw beste beoordeling.

4. Wanneer u klaar bent, klikt u op de **knop** Verzenden.

   ![Voorbeeld van nieuwe URL-inzending](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Een verdachte URL naar Microsoft verzenden

1. Selecteer URL **in de sectie Selecteer** het inzendingstype.  Voer in het vak dat wordt weergegeven de volledige URL in `https://www.fabrikam.com/marketing.html` (bijvoorbeeld).

2. Selecteer in **de sectie** Reden voor inzending een van de volgende opties:

   - **Had niet moeten worden geblokkeerd**

   - **Moet zijn geblokkeerd:** Selecteer **Phishing** of **Malware.**

3. Wanneer u klaar bent, klikt u op de **knop** Verzenden.

   ![Voorbeeld van nieuwe e-mailinzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>Een verdachte e-mailbijlage indienen bij Microsoft

1. Selecteer in **de sectie Selecteer het inzendingstype** de optie **E-mailbijlage**.

2. Klik **op Bestand kiezen.** Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en klik vervolgens op **Openen.**

3. Selecteer in **de sectie** Reden voor inzending een van de volgende opties:

   - **Had niet moeten worden geblokkeerd**

   - **Moet zijn geblokkeerd:** **Malware** is de enige keuze en wordt automatisch geselecteerd.

4. Wanneer u klaar bent, klikt u op de **knop** Verzenden.

   ![Voorbeeld van nieuwe bijlageinzending](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>Items weergeven die zijn ingediend voor analyse

Ga in Microsoft 365 beveiligingscentrum naar **Inzendingen** en controleer of u zich op het tabblad **Ingediend voor analyse** hebt

Op de opdrachtbalk in het midden van de pagina kunt u een begindatum, een einddatum en (standaard) filteren op Indienings-id **(een** GUID-waarde die aan elke inzending is toegewezen) door een waarde in het vak in te voeren en op Knop Vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken. U kunt meerdere waarden invoeren die zijn gescheiden door komma's.

Als u de filtercriteria wilt wijzigen, klikt u op de **knop Filter** en kiest u een van de volgende waarden:

- **Afzender**
- **Onderwerp/URL/bestandsnaam**
- **Ingediend door**
- **Inzendingstype**
- **Status**

![Nieuwe filteropties voor beheerdersinzendingen](../../media/admin-submission-email-filter-options.png)

Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.** Sla in het dialoogvenster dat wordt weergegeven het .csv op.

Onder de grafiek ziet u drie tabbladen: **E-mail** (standaard), **URL** en **E-mailbijlage.**

### <a name="view-admin-email-submissions"></a>E-mailberichten van beheerders weergeven

U kunt onder aan de pagina op de knop **Kolommen** aanpassen klikken om kolommen toe te voegen of te verwijderen uit de weergave:

- **Datum**
- **Inzending-id:** een GUID-waarde die aan elke inzending is toegewezen.
- **Ingediend door**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **Ip-afzender**<sup>\*</sup>
- **Inzendingstype**
- **Bezorgingsreden**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

#### <a name="admin-submission-rescan-details"></a>Details van de inzending van beheerders opnieuw scannen

Berichten die worden verzonden in beheerdersinzendingen, worden opnieuw gescand en de resultaten worden weergegeven in de flyout met inzendingendetails:

- Of er tijdens de levering een fout zat in de e-mailverificatie van de afzender.
- Informatie over eventuele beleidstreffers die het oordeel over een bericht kunnen hebben beïnvloed of overschreven.
- Huidige deactiveringsresultaten om te zien of de URL's of bestanden in het bericht schadelijk waren of niet.
- Feedback van cijferaars.

Als een overschrijving is gevonden, zou het opnieuw scannen in enkele minuten moeten zijn voltooid. Als er geen probleem was bij e-mailverificatie of bezorging werd niet beïnvloed door een overschrijven, kan de feedback van cijferaars maximaal een dag duren.

### <a name="view-admin-url-submissions"></a>URL-inzendingen voor beheerders weergeven

Klik op **het tabblad URL.**

U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:

- **Datum**
- **Inzending-id**
- **Ingediend door**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Inzendingstype**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

### <a name="view-email-attachment-submissions"></a>E-mailbijlage-inzendingen weergeven

Klik op **het tabblad** Bijlagen.

U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:

- **Datum**
- **Inzending-id**
- **Ingediend door**<sup>\*</sup>
- **Bestandsnaam**<sup>\*</sup>
- **Inzendingstype**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

## <a name="view-user-submissions-to-microsoft"></a>Gebruikersinzendingen weergeven bij Microsoft

Als u de invoeging Rapportbericht , de [invoeging](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md)melden of personen de ingebouwde rapportage [in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)op internet hebben  geïmplementeerd, kunt u zien wat gebruikers rapporteren op het tabblad Gebruikersinzendingen.

1. Ga in het & Compliancecentrum naar **Threat management** \> **Submissions**.

2. Selecteer het **tabblad Gebruikersinzendingen** en klik vervolgens op **Nieuwe inzending.**

U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:

- **Verzonden op**
- **Ingediend door**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **Ip-afzender**<sup>\*</sup>
- **Inzendingstype**

<sup>\*</sup> Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren op Afzender door een waarde in het vak in te voeren en op knop Vernieuwen te  ![ ](../../media/scc-quarantine-refresh.png) klikken. U kunt meerdere waarden invoeren die zijn gescheiden door komma's.

Als u de filtercriteria wilt wijzigen, klikt u op de knop **Afzender** en kiest u een van de volgende waarden:

- **Afzenderdomein**
- **Onderwerp**
- **Ingediend door**
- **Inzendingstype**
- **Ip-afzender**

![Nieuwe filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.** Sla in het dialoogvenster dat wordt weergegeven het .csv op.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Gebruikersinzendingen weergeven in het aangepaste postvak

**Als** u een [aangepast](user-submission.md) postvak hebt geconfigureerd om gerapporteerde berichten van gebruikers te ontvangen, kunt u berichten bekijken en verzenden die zijn bezorgd in het rapportpostvak.

1. Ga in het & Compliancecentrum naar **Threat management** \> **Submissions**.

2. Selecteer het **tabblad Aangepast postvak.**

U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:

- **Verzonden op**
- **Ingediend door**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **Ip-afzender**<sup>\*</sup>
- **Inzendingstype**

Boven aan de pagina kunt u een begindatum, een einddatum  en u kunt filteren op Ingediend door een waarde in het vak in te voeren en op knop ![ Vernieuwen te ](../../media/scc-quarantine-refresh.png) klikken. U kunt meerdere waarden invoeren die zijn gescheiden door komma's.

Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.** Sla in het dialoogvenster dat wordt weergegeven het .csv op.

> [!NOTE]
> Als organisaties zijn geconfigureerd om alleen naar een aangepast postvak te verzenden, worden gerapporteerde berichten niet opnieuw verzonden en zijn de resultaten in de portal Gebruikers gerapporteerde berichten altijd leeg.

## <a name="undo-user-submissions"></a>Gebruikersinzendingen ongedaan maken

Wanneer een gebruiker een verdachte e-mail naar het aangepaste postvak heeft verzonden, hebben de gebruiker en beheerder geen optie om de inzending ongedaan te maken. Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of Ongewenste e-mail.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Berichten verzenden naar Microsoft vanuit het aangepaste postvak

Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en verzenden naar Microsoft voor analyse. Hiermee wordt een inzending van een gebruiker daadwerkelijk verplaatst naar een beheerdersinzending.

Selecteer op **het tabblad Gerapporteerde** berichten van gebruiker  een bericht in de lijst, klik op de knop Actie en maak een van de volgende selecties:

- **Rapport opschoon**
- **Phishing melden**
- **Malware rapporteren**
- **Spam rapporteren**

![Nieuwe opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
