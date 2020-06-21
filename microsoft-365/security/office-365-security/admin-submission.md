---
title: Beheerdersinzendingen
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
description: Beheerders kunnen leren hoe ze de portal Voor inzendingen in het Security & Compliance Center kunnen gebruiken om verdachte e-mails, vermoedelijke phishingmails, spam en andere mogelijk schadelijke berichten, URL's en bestanden bij Microsoft in te dienen om te scannen.
ms.openlocfilehash: 18941c1400917291f8924331fd19827e476db914
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726848"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Beheerdersinzending gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft

In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal Submissions in het Security & Compliance Center gebruiken om e-mailberichten, URL's en bijlagen bij Microsoft in te dienen om te scannen.

Wanneer u een e-mail indient, ontvangt u informatie over beleidsregels die de binnenkomende e-mail mogelijk hebben toegestaan bij uw tenant, evenals het onderzoeken van URL's en bijlagen in de e-mail. Beleidsregels die een e-mail mogelijk hebben toegestaan, bevatten de lijst met veilige afzenders van een individuele gebruiker en beleid op tenantniveau, zoals Exchange-e-mailstroomregels (ook wel transportregels genoemd).

Zie [Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, URL's en bijlagen naar Microsoft te verzenden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **pagina Indiening** wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .

- U moet machtigingen krijgen voordat u de procedures in dit onderwerp uitvoeren:

  - Als u berichten en bestanden wilt verzenden bij Microsoft, moet u lid zijn van een van de volgende rolgroepen:

    - **Organisatiebeheer** of **beveiligingsbeheerder** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **hygiënebeheer** in [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)

  - Voor alleen-lezen toegang tot de portal Voor inzendingen moet u lid zijn van een van de volgende rolgroepen:

    - **Security Reader** in het [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-weergeven organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Zie [Berichten en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)meer informatie over hoe gebruikers berichten en bestanden naar Microsoft kunnen verzenden.

## <a name="report-suspicious-content-to-microsoft"></a>Verdachte inhoud melden aan Microsoft

1. Ga in het Security & Compliance Center naar **Threat management** \> **Review** \> **Admin-berichten**.

2. Klik op de pagina **Inzendingen** die wordt weergegeven op de knop **Nieuwe inzending.**

3. Gebruik de flyout **voor nieuwe indiening** die het bericht, de URL of de bijlage lijkt in te dienen, zoals beschreven in de volgende secties.

### <a name="submit-a-questionable-email-to-microsoft"></a>Een twijfelachtige e-mail verzenden naar Microsoft

1. Selecteer **E-mail**in de sectie **Objecttype** . Gebruik in de sectie **Weergave een** van de volgende opties:

   - **Netwerkbericht-id:** dit is een GUID-waarde die beschikbaar is in de kop **X-MS-Exchange-Organization-Network-Message-Id** in het bericht.

   - **Bestand**: Klik op **Bestand kiezen**. Zoek en selecteer in het dialoogvenster dat het .eml- of .msg-bestand opent en klik vervolgens op **Openen**.

2. Geef in de sectie **Geadresseerden** een of meer ontvangers op waartegen u een beleidscontrole wilt uitvoeren. De beleidscontrole bepaalt of de e-mail het scannen heeft omzeild vanwege het gebruikers- of organisatiebeleid.

3. Selecteer in de sectie **Reden voor indiening** een van de volgende opties:

   - **Had niet geblokkeerd moeten worden**

   - **Moet zijn geblokkeerd:** Selecteer **Spam,** **Phishing**of **Malware**. Als je het niet zeker weet, gebruik dan je beste oordeel.

4. Als het filter is omzeild vanwege beleid bij indiening, ziet u informatie over dat beleid.

   Als het filter niet is omzeild vanwege een of meer beleidsregels, wordt de scan binnen enkele minuten voltooid. U ziet aanvullende informatie over de indiening door op de statuskoppeling te klikken. Dit omvat de resultaten van de beleidscontrole en het herscanvonnis. Houd er rekening mee dat de e-mail niet opnieuw wordt uitgevoerd via de volledige filterstapel van Office 365 ATP, maar een gedeeltelijke rescan uitvoert op basis van bepaalde kenmerken van de e-mail, URL of bestand.

5. Als u klaar bent, klikt u op **Verzenden.**

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Een verdachte URL naar Microsoft verzenden

1. Selecteer **URL**in de sectie **Objecttype** . Voer in het vak dat wordt weergegeven de volledige URL in (bijvoorbeeld <https://www.fabrikam.com/marketing.html> ).

2. Selecteer in de sectie **Reden voor indiening** een van de volgende opties:

   - **Had niet geblokkeerd moeten worden**

   - **Moet zijn geblokkeerd:** Selecteer **Phishing** of **Malware**.

3. Als u klaar bent, klikt u op **Verzenden.**

![Voorbeeld van e-mailinzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Een verdacht bestand indienen bij Microsoft

1. Selecteer bijlage in de sectie **Objecttype** **.**

2. Klik **op Bestand kiezen**. Zoek en selecteer het bestand in het dialoogvenster dat wordt geopend en selecteer het bestand en klik vervolgens op **Openen**.

3. Selecteer in de sectie **Reden voor indiening** een van de volgende opties:

   - **Had niet geblokkeerd moeten worden**

   - **Moet zijn geblokkeerd**: **Malware** is de enige keuze, en wordt automatisch geselecteerd..

4. Als u klaar bent, klikt u op **Verzenden.**

![Voorbeeld van bijlageinzending](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Beheerdersinzendingen bekijken

1. Ga in het Security & Compliance Center naar **Threat management** \> **Review** \> **Admin-berichten**.

2. Controleer op de pagina **Inzendingen** dat wordt weergegeven of het tabblad **Beheerdersinzendingen** is geselecteerd.

Boven aan de pagina u een begindatum, een einddatum invoeren en (standaard) u filteren op **inzendings-id** door een waarde in het vak in te voeren en op vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken. U meerdere waarden invoeren die door komma's zijn gescheiden.

Als u de filtercriteria wilt wijzigen, klikt u op de knop **Indienings-id** en kiest u een van de volgende waarden:

- **Afzender**
- **Onderwerp/URL/bestandsnaam**
- **Afkomstig**
- **Indieningstype**
- **Status**

![Filteropties voor beheerdersinzendingen](../../media/admin-submission-email-filter-options.png)

Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina exporteren en selecteert u **Grafiekgegevens** of **tabel**. Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.

Onder de grafiek bevinden zich drie tabbladen: **E-mail** (standaard), **URL**en **Bijlage**.

### <a name="view-admin-email-submissions"></a>E-mailinzendingen voor beheerders bekijken

Klik op het tabblad **E-mail.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Datum**
- **Indienings-id**
- **Afkomstig**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **IP-adres van afzender**<sup>\*</sup>
- **Indieningstype**
- **Reden voor levering**
- **Status**<sup>\*</sup>
- **Besturingstype**
- **Controlebron**

  <sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

### <a name="view-admin-url-submissions"></a>Beheerders-URL-inzendingen weergeven

Klik op het tabblad **URL.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Datum**
- **Indienings-id**
- **Afkomstig**<sup>\*</sup>
- **Url**<sup>\*</sup>
- **Indieningstype**
- **Status**<sup>\*</sup>

  <sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

### <a name="view-admin-attachment-submissions"></a>Beheerdersbijlagen weergeven

Klik op het tabblad **Bijlagen.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Datum**
- **Indienings-id**
- **Afkomstig**<sup>\*</sup>
- **Bestandsnaam**<sup>\*</sup>
- **Indieningstype**
- **Status**<sup>\*</sup>

  <sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

## <a name="view-user-submissions-to-microsoft"></a>Gebruikersinzendingen bij Microsoft weergeven

Als u de [invoegtoepassing Rapportbericht](enable-the-report-message-add-in.md)hebt geïmplementeerd of als mensen de [ingebouwde rapportage in de webversie](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)van Outlook gebruiken, u zien wat gebruikers rapporteren op het tabblad **Gebruikersinzendingen.**

1. Ga in het Security & Compliance Center naar **Threat management** \> **Review** \> **Admin-berichten**.

2. Klik op de pagina **Inzendingen** die wordt weergegeven op het tabblad **Gebruikersinzendingen.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Ingediend op**
- **Afkomstig**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **IP-adres van afzender**<sup>\*</sup>
- **Indieningstype**

<sup>\*</sup>Als u op deze waarde klikt, wordt gedetailleerde informatie weergegeven in een flyout.

Boven aan de pagina u een begindatum, een einddatum invoeren en (standaard) u filteren op **afzender** door een waarde in het vak in te voeren en op vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken. U meerdere waarden invoeren die door komma's zijn gescheiden.

Als u de filtercriteria wilt wijzigen, klikt u op de knop **Afzender** en kiest u een van de volgende waarden:

- **Afzenderdomein**
- **Onderwerp**
- **Afkomstig**
- **Indieningstype**
- **IP-adres van afzender**

![Filteropties voor gebruikersinzendingen](../../media/user-submissions-filter-options.png)

Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina exporteren en selecteert u **Grafiekgegevens** of **tabel**. Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Gebruikersinzendingen weergeven in het aangepaste postvak

Als u [een aangepast postvak](user-submission.md) hebt geconfigureerd om gerapporteerde berichten van gebruikers te ontvangen, u berichten bekijken en verzenden die zijn bezorgd in het rapportpostvak.

1. Ga in het Security & Compliance Center naar **Threat management** \> **Review** \> **Admin-berichten**.

2. Klik op de pagina **Inzendingen** die wordt weergegeven op het tabblad **Aangepast postvak.**

U onder aan de pagina op de knop **Kolomopties** klikken om kolommen uit de weergave toe te voegen of te verwijderen:

- **Ingediend op**
- **Afkomstig**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **IP-adres van afzender**<sup>\*</sup>
- **Indieningstype**

Boven aan de pagina u een begindatum, een einddatum invoeren en u filteren op **Ingezonden door** een waarde in het vak in te voeren en op Vernieuwen te ![ ](../../media/scc-quarantine-refresh.png) klikken. U meerdere waarden invoeren die door komma's zijn gescheiden.

Als u de resultaten wilt exporteren, **klikt** u boven aan de pagina exporteren en selecteert u **Grafiekgegevens** of **tabel**. Sla in het dialoogvenster dat wordt weergegeven het CSV-bestand op.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Berichten verzenden naar Microsoft vanuit het aangepaste postvak

Als u het aangepaste postvak hebt geconfigureerd om door gebruikers gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, u specifieke berichten voor analyse naar Microsoft zoeken en verzenden. Hierdoor wordt een gebruiker effectief naar een beheerdersinzending verplaatst.

Selecteer op het tabblad **Aangepast postvak** een bericht in de lijst, klik op de knop **Actie** en maak een van de volgende selecties:

- **Rapport schoon**
- **Phishing melden**
- **Malware melden**
- **Spam melden**

![Opties op de knop Actie](../../media/user-submission-custom-mailbox-action-button.png)
