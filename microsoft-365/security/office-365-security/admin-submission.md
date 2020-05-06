---
title: Beheerdersinzendingen in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het verzenden van verdachte e-mails, vermoedelijke phishingmails, spam en andere mogelijk schadelijke berichten, URL's en bestanden van uw bedrijf bij Microsoft voor het scannen.
ms.openlocfilehash: 79f200963655e5fb07a04b686c1dd8cc3bbd0873
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034198"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Beheerbeheer gebruiken om vermoedelijke spam, phish, URL's en bestanden bij Microsoft in te dienen

Als u een beheerder bent in een Microsoft 365-organisatie met postvakken in Exchange Online, u de inzendingenportal in het Beveiligingscentrum & Compliance Center gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen om te scannen.

Wanneer u een e-mail indient, ontvangt u informatie over het beleid dat de binnenkomende e-mail mogelijk in uw tenant heeft toegestaan, evenals het onderzoeken van URL's en bijlagen in de e-mail. Beleidsregels waarmee een e-mail mogelijk is toegestaan, bevatten de lijst met veilige afzenders van een individuele gebruiker en beleid op tenantniveau, zoals de regels voor de e-mailstroom van Exchange (ook wel transportregels genoemd).

Zie [Berichten en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)andere manieren om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de <https://protection.office.com/reportsubmission>pagina **Indiening** wilt gaan, gebruikt u .

- U moet beschikken over bepaalde machtigingen om deze procedures te kunnen uitvoeren. Als u antispambeleid wilt toevoegen, wijzigen en verwijderen, moet u lid zijn van de rolgroepen **Organisatiebeheer,** **Beveiligingsbeheerder**of **Beveiligingslezer.** Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.

- Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over hoe gebruikers berichten en bestanden kunnen verzenden naar [Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Verdachte inhoud melden aan Microsoft

1. Ga in het Security & Compliance Center **naar** \> Berichten **voor** \> het indienen van meldingen voor **het verzenden van beheerbeheer.**

2. Klik op de pagina **Inzendingen** die wordt weergegeven op de knop **Nieuwe inzending.**

3. Gebruik **Nieuwe flyout voor indiening** die wordt weergegeven om het bericht, de URL of de bijlage in te dienen, zoals beschreven in de volgende secties.

### <a name="submit-a-questionable-email-to-microsoft"></a>Een twijfelachtige e-mail verzenden naar Microsoft

1. Selecteer **E-mail**in de sectie **Objecttype** . Gebruik in de sectie **Indieningsvorm** een van de volgende opties:

   - **Netwerkbericht-id:** dit is een GUID-waarde die beschikbaar is in de header **X-MS-Exchange-Organization-Network-Message-Id** in het bericht.

   - **Bestand:** klik op **Bestand kiezen**. Zoek en selecteer in het dialoogvenster dat wordt geopend het bestand .eml of .msg en klik vervolgens op **Openen**.

2. Geef **in** de sectie Ontvangers een of meer ontvangers op waartegen u een beleidscontrole wilt uitvoeren. De beleidscontrole bepaalt of de e-mail scannen heeft omzeild vanwege het gebruikers- of organisatiebeleid.

3. Selecteer in de sectie **Reden voor indiening** een van de volgende opties:

   - **Had niet mogen worden geblokkeerd**

   - **Had moeten worden geblokkeerd**: Selecteer **Spam,** **Phishing**of **Malware**. Als je het niet zeker weet, gebruik dan je beste oordeel.

4. Als het filter is omzeild vanwege het beleid bij indiening, ziet u informatie over dat beleid.

   Als het filter niet is omzeild vanwege een of meer beleidsregels, wordt de scan binnen enkele minuten voltooid. U ziet aanvullende informatie over de indiening door op de statuskoppeling te klikken. Dit omvat de resultaten van de beleidscontrole en het rescanvonnis. Houd er rekening mee dat de e-mail niet opnieuw wordt uitgevoerd via de volledige filterstapel van Office 365 ATP, maar dat er een gedeeltelijke recan wordt uitgevoerd op basis van bepaalde kenmerken van de e-mail, URL of het bestand.

5. Klik op **Verzenden** als u klaar bent.

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Een verdachte URL naar Microsoft verzenden

1. Selecteer **URL**in de sectie **Objecttype** . Voer in het vak dat wordt weergegeven <https://www.fabrikam.com/marketing.html>de volledige URL in (bijvoorbeeld).

2. Selecteer in de sectie **Reden voor indiening** een van de volgende opties:

   - **Had niet mogen worden geblokkeerd**

   - **Had moeten worden geblokkeerd**: Selecteer **Phishing** of **Malware**.

3. Klik op **Verzenden** als u klaar bent.

![Voorbeeld van e-mailindiening](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Een verdacht bestand indienen bij Microsoft

1. Selecteer **bijlage**in de sectie **Objecttype** .

2. Klik **op Bestand kiezen**. Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en selecteer het bestand en klik vervolgens op **Openen**.

3. Selecteer in de sectie **Reden voor indiening** een van de volgende opties:

   - **Had niet mogen worden geblokkeerd**

   - **Moet zijn geblokkeerd**: **Malware** is de enige keuze, en wordt automatisch geselecteerd..

4. Klik op **Verzenden** als u klaar bent.

![Voorbeeld van het indienen van bijlagen](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Beheerdersinzendingen weergeven

1. Ga in het Security & Compliance Center **naar** \> Berichten **voor** \> het indienen van meldingen voor **het verzenden van beheerbeheer.**

2. Controleer op de pagina **Inzendingen** die wordt weergegeven of het tabblad **Inzendingen beheerder** is geselecteerd.

Boven aan de pagina u een begindatum, een einddatum en (standaard) filteren op **indienings-id** door ![een](../../media/scc-quarantine-refresh.png)waarde in het vak in te voeren en op Knop Vernieuwen te klikken. U meerdere waarden invoeren die zijn gescheiden door komma's.

Als u de filtercriteria wilt wijzigen, klikt u op de knop **Indiening-id** en kiest u een van de volgende waarden:

- **Afzender**
- **Onderwerp/URL/bestandsnaam**
- **Afkomstig**
- **Type inzending**
- **Status**

![Filteropties voor beheerdersinzendingen](../../media/admin-submission-email-filter-options.png)

Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel**. Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.

Onder de grafiek staan drie tabbladen: **E-mail** (standaard), **URL**en **bijlage**.

### <a name="view-admin-email-submissions"></a>E-mailinzendingen voor beheerders weergeven

Klik op het tabblad **E-mail.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Datum**
- **Inzendings-ID**
- **Afkomstig**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **Ip-afzender**<sup>\*</sup>
- **Type inzending**
- **Leveringsreden**
- **Status**<sup>\*</sup>
- **Besturingstype**
- **Controlebron**

  <sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

### <a name="view-admin-url-submissions"></a>URL-inzendingen voor beheerders weergeven

Klik op het **tabblad URL.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Datum**
- **Inzendings-ID**
- **Afkomstig**<sup>\*</sup>
- **Url**<sup>\*</sup>
- **Type inzending**
- **Status**<sup>\*</sup>

  <sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

### <a name="view-admin-attachment-submissions"></a>Inzendingen voor beheerdersbijlagen weergeven

Klik op het tabblad **Bijlagen.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Datum**
- **Inzendings-ID**
- **Afkomstig**<sup>\*</sup>
- **Bestandsnaam**<sup>\*</sup>
- **Type inzending**
- **Status**<sup>\*</sup>

  <sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

## <a name="view-user-submissions-to-microsoft"></a>Inzendingen van gebruikers bij Microsoft weergeven

Als u de [invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md)hebt geïmplementeerd of als mensen de [ingebouwde rapportage gebruiken in de webversie van Outlook,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)u zien welke gebruikers rapporteren op het tabblad **Gebruikersinzendingen.**

1. Ga in het Security & Compliance Center **naar** \> Berichten **voor** \> het indienen van meldingen voor **het verzenden van beheerbeheer.**

2. Klik op de pagina **Inzendingen** die wordt weergegeven op het tabblad **Gebruikersinzendingen.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Ingediend op**
- **Afkomstig**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **Ip-afzender**<sup>\*</sup>
- **Type inzending**

<sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

Boven aan de pagina u een begindatum, een einddatum en (standaard) filteren op **afzender** door een ![waarde](../../media/scc-quarantine-refresh.png)in het vak in te voeren en op Knop Vernieuwen te klikken. U meerdere waarden invoeren die zijn gescheiden door komma's.

Als u de filtercriteria wilt wijzigen, klikt u op de knop **Afzender** en kiest u een van de volgende waarden:

- **Afzenderdomein**
- **Onderwerp**
- **Afkomstig**
- **Type inzending**
- **Ip-afzender**

![Filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel**. Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Inzendingen van gebruikers weergeven in het aangepaste postvak

Als u [een aangepast postvak](user-submission.md) hebt geconfigureerd om gerapporteerde berichten van gebruikers te ontvangen, u berichten die zijn afgeleverd in het rapportagepostvak bekijken en verzenden.

1. Ga in het Security & Compliance Center **naar** \> Berichten **voor** \> het indienen van meldingen voor **het verzenden van beheerbeheer.**

2. Klik op de pagina **Inzendingen** die wordt weergegeven op het tabblad **Aangepast postvak.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Ingediend op**
- **Afkomstig**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **Ip-afzender**<sup>\*</sup>
- **Type inzending**

Boven aan de pagina u een begindatum, een einddatum invoeren en u filteren op **Verzenden door** een waarde in het vak in te voeren en op knop Vernieuwen te ![](../../media/scc-quarantine-refresh.png)klikken. U meerdere waarden invoeren die zijn gescheiden door komma's.

Als u de resultaten wilt exporteren, klikt u op **Exporteren** boven aan de pagina en selecteert u **Grafiekgegevens** of **Tabel**. Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Berichten verzenden naar Microsoft vanuit het aangepaste postvak

Als u het aangepaste postvak hebt geconfigureerd om door gebruikers gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, u specifieke berichten voor analyse naar Microsoft zoeken en verzenden. Hiermee wordt een gebruiker inplaats gezet in een beheerdersinzending.

Selecteer op het tabblad **Aangepast postvak** een bericht in de lijst, klik op de knop **Actie** en maak een van de volgende selecties:

- **Rapport schoon**
- **Phishing melden**
- **Malware melden**
- **Spam melden**

![Opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
