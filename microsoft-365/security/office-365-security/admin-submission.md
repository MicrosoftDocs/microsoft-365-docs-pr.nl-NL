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
description: Beheerders kunnen leren hoe ze de portal Inzendingen in het beveiligings- & compliancecentrum kunnen gebruiken om verdachte e-mailberichten, vermoedelijke phishingmails, spam en andere potentieel schadelijke berichten, URL's en bestanden naar Microsoft te verzenden voor scannen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: beeca51b50a7a60db9663220d9a5b3cee2eac56f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927106"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)


In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal Inzendingen in het beveiligings- &-compliancecentrum gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen voor scannen.

Wanneer u een e-mailbericht indient, krijgt u het volgende:

1. **Controle voor e-mailverificatie:** Details over het al dan niet geslaagd zijn van e-mailverificatie wanneer deze is bezorgd.
2. **Beleidstreffers:** Informatie over beleidsregels die de inkomende e-mail mogelijk hebben toegestaan of geblokkeerd in uw tenant, waardoor onze servicefilters worden overgenomen.
3. **Payload reputation/detonation**: Onderzoek van URL's en bijlagen in het bericht.
4. **Beoordelingsanalyse:** controleren door menselijke cijferaars om te controleren of berichten schadelijk zijn of niet.

> [!IMPORTANT]
> Payload reputation/detonation and grader analysis are not done in all tenants. Informatie wordt geblokkeerd om buiten de organisatie te gaan wanneer gegevens niet de tenantgrens moeten verlaten voor nalevingsdoeleinden.

Zie Berichten en bestanden rapporteren bij Microsoft voor andere manieren om e-mailberichten, URL's en bijlagen bij [Microsoft in te dienen.](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de pagina **Inzending** wilt gaan, gebruikt <https://protection.office.com/reportsubmission> u .

- Als u berichten en bestanden wilt verzenden naar Microsoft, moet u lid zijn van een van de volgende rollengroepen:

  - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).

  - **Organisatiebeheer** in [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)

    Houd er rekening mee dat lidmaatschap van deze rollengroep vereist is om gebruikersinzendingen in het aangepaste [postvak](#view-user-submissions-to-the-custom-mailbox) weer te geven, zoals verder wordt beschreven in dit artikel.

- Zie Berichten en bestanden rapporteren bij Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen [bij Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Verdachte inhoud rapporteren aan Microsoft

1. Ga in het & Compliancecentrum naar Threat **management** \> **Submissions,** controleer of  u zich op het tabblad Beheerdersinzendingen en klik vervolgens op **Nieuwe inzending.**

2. Gebruik **flyout Nieuwe** inzending die wordt weergegeven om het bericht, de URL of de bijlage in te dienen, zoals wordt beschreven in de volgende secties.

### <a name="submit-a-questionable-email-to-microsoft"></a>Een twijfelachtige e-mail verzenden naar Microsoft

1. Selecteer **e-mail** in de sectie **Objecttype.** Gebruik in **de sectie Inzendingsindeling** een van de volgende opties:

   - **Netwerkbericht-id:** dit is een GUID-waarde die beschikbaar is in de **koptekst X-MS-Exchange-Organization-Network-Message-Id** in het bericht of in de **X-MS-Office365-Filtering-Correlation-Id-header** in in quarantaine geplaatste berichten.

   - **Bestand:** Klik op **Bestand kiezen.** Zoek en selecteer in het dialoogvenster dat wordt geopend het .eml- of .msg-bestand en klik vervolgens op **Openen.**

   > [!NOTE]
   > Beheerders met Defender voor Office 365-abonnement 1 of Abonnement 2 kunnen berichten vanaf 30 dagen verzenden. Andere beheerders kunnen slechts 7 dagen teruggaan.

2. Geef in **de sectie Geadresseerden** een of meer geadresseerden op tegen wie u een beleidscontrole wilt uitvoeren. Met de beleidscontrole wordt bepaald of het scannen per e-mail is overgeslagen vanwege gebruikers- of organisatiebeleid.

3. Selecteer in **de sectie** Reden voor inzending een van de volgende opties:

   - **Had niet moeten worden geblokkeerd**

   - **Moet zijn geblokkeerd:** Selecteer **Spam,** **Phishing** of **Malware.** Als u het niet zeker weet, gebruikt u uw beste beoordeling.

4. Wanneer u klaar bent, klikt u op de **knop** Verzenden.

   ![Voorbeeld van URL-inzending](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Een verdachte URL naar Microsoft verzenden

1. Selecteer URL in de sectie **Objecttype.**  Voer in het vak dat wordt weergegeven de volledige URL in `https://www.fabrikam.com/marketing.html` (bijvoorbeeld).

2. Selecteer in **de sectie** Reden voor inzending een van de volgende opties:

   - **Had niet moeten worden geblokkeerd**

   - **Moet zijn geblokkeerd:** Selecteer **Phishing** of **Malware.**

3. Wanneer u klaar bent, klikt u op de **knop** Verzenden.

   ![Voorbeeld van e-mail indienen](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Een verdacht bestand indienen bij Microsoft

1. Selecteer bijlage in de sectie **Objecttype.** 

2. Klik **op Bestand kiezen.** Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en klik vervolgens op **Openen.**

3. Selecteer in **de sectie** Reden voor inzending een van de volgende opties:

   - **Had niet moeten worden geblokkeerd**

   - **Moet zijn geblokkeerd:** **Malware** is de enige keuze en wordt automatisch geselecteerd..

4. Wanneer u klaar bent, klikt u op de **knop** Verzenden.

   ![Voorbeeld van bijlageinzending](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Beheerdersinzendingen weergeven

Ga in het & Compliancecentrum naar Threat **management** \> **Submissions,** controleer of  u zich op het tabblad Beheerdersinzendingen en klik vervolgens op **Nieuwe inzending.**

Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren op Indienings-id **(een** GUID-waarde die aan elke inzending is toegewezen) door een waarde in het vak in te voeren en op Knop Vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken. U kunt meerdere waarden invoeren die zijn gescheiden door komma's.

Als u de filtercriteria wilt wijzigen, klikt u op de knop **Indiening-id** en kiest u een van de volgende waarden:

- **Afzender**
- **Onderwerp/URL/bestandsnaam**
- **Ingediend door**
- **Inzendingstype**
- **Status**

![Filteropties voor beheerdersinzendingen](../../media/admin-submission-email-filter-options.png)

Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.** Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.

Onder de grafiek vindt u drie tabbladen: **E-mail** (standaard), **URL** en **Bijlage.**

### <a name="view-admin-email-submissions"></a>E-mailberichten van beheerders weergeven

Klik op **het tabblad E-mail.**

U kunt op de **knop Kolomopties** onder aan de pagina klikken om kolommen toe te voegen of te verwijderen uit de weergave:

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

Berichten die worden verzonden in beheerdersinzendingen, worden opnieuw gescand en de resultaten worden weergegeven in de details flyout:

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

### <a name="view-admin-attachment-submissions"></a>Bijlagen van beheerders bekijken

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

Als u de invoegversie van rapportbericht, de [invoegversie](enable-the-report-message-add-in.md)van [Rapport phishing](enable-the-report-phish-add-in.md)of personen de ingebouwde rapportage in de  [webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)van Outlook hebt geïmplementeerd, kunt u zien wat gebruikers rapporteren op het tabblad Gebruikersinzendingen.

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

![Filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.** Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.

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

Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina op Exporteren en selecteert u **Grafiekgegevens** of **Tabel.** Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.

## <a name="undo-user-submissions"></a>Gebruikersinzendingen ongedaan maken

Wanneer een gebruiker een verdachte e-mail naar het aangepaste postvak heeft verzonden, hebben de gebruiker en beheerder geen optie om de inzending ongedaan te maken. Als de gebruiker de e-mail wil herstellen, is deze beschikbaar voor herstel in de mappen Verwijderde items of Ongewenste e-mail.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Berichten verzenden naar Microsoft vanuit het aangepaste postvak

Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en verzenden naar Microsoft voor analyse. Hiermee wordt een inzending van een gebruiker daadwerkelijk verplaatst naar een beheerdersinzending.

Selecteer op **het tabblad** Aangepast postvak een  bericht in de lijst, klik op de knop Actie en maak een van de volgende selecties:

- **Rapport opschoon**
- **Phishing melden**
- **Malware rapporteren**
- **Spam rapporteren**

![Opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)