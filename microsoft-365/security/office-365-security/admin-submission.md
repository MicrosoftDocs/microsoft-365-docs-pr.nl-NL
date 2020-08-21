---
title: Admin-inzendingen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie over het gebruik van de portal voor uitnodigingen van de beveiligings & nalevings centrum voor het verzenden van verdachte e-mailberichten, verdachte e-mailberichten, spam en andere mogelijk schadelijke berichten, Url's en bestanden aan Microsoft voor het scannen.
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845964"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Gebruik beheer ter verzending om verdachte spam, phishing, Url's en bestanden bij Microsoft te verzenden.

In Microsoft 365-organisaties met postvakken in Exchange Online kunnen beheerders de portal voor ingediende vragen in het beveiligings & nalevings centrum gebruiken voor het verzenden van e-mailberichten, Url's en bijlagen bij Microsoft voor het scannen.

Wanneer u een e-mailbericht verzendt, krijgt u informatie over de beleidsregels die de inkomende e-mail in uw Tenant hebben toegestaan en van het onderzoek van Url's en bijlagen in het e-mailbericht. Beleidsregels die een e-mailbericht kunnen hebben, bestaan uit de lijst met veilige afzenders van een individuele gebruiker en beleid voor tenantniveau, zoals Exchange-e-mail stroom regels (ook wel transport-regels genoemd).

Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor andere manieren om e-mailberichten, url's en bijlagen bij Microsoft in te dienen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>. Als u rechtstreeks naar de **Verzend** pagina wilt gaan, gebruikt u <https://protection.office.com/reportsubmission> .

- U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:

  - Als u berichten en bestanden bij Microsoft wilt verzenden, moet u lid zijn van een van de volgende rollen groepen:

    - **Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Voor alleen-lezen toegang tot de portal van ingediende items moet u lid zijn van een van de volgende rollen groepen:

    - **Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).
    - **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Zie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md)voor meer informatie over hoe gebruikers berichten en bestanden kunnen indienen bij Microsoft.

## <a name="report-suspicious-content-to-microsoft"></a>Verdachte inhoud rapporteren aan Microsoft

1. Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions**, ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.

2. Gebruik de nieuwe flyout voor **indienen** die wordt weergegeven om het bericht, de URL of de bijlage te verzenden, zoals beschreven in de volgende secties.

### <a name="submit-a-questionable-email-to-microsoft"></a>Een dubieuze e-mail naar Microsoft verzenden

1. Selecteer in de sectie **object type** de optie **e-mail**. Gebruik een van de volgende opties in de sectie **opmaak van indiening** .

   - **Netwerkbericht-id**: dit is een GUID-waarde die beschikbaar is in de header **X-MS-Exchange-Organization-Network-Message-ID** in het bericht.

   - **Bestand**: Klik op **bestand kiezen**. In het dialoogvenster dat wordt geopend, zoekt en selecteert u het bestand. eml of. msg en klikt u vervolgens op **openen**.

2. Geef in de sectie **geadresseerden** een of meer geadresseerden op waarvoor u een beleid wilt uitvoeren. Met de beleidscontrole wordt bepaald of het e-mailbericht dat wordt genegeerd vanwege het beleid van de gebruiker of organisatie.

3. Selecteer een van de volgende opties in de sectie **reden voor indiening** .

   - **Mag niet zijn geblokkeerd**

   - **Is geblokkeerd**: Selecteer **spam**, **phishing**of **malware**. Als u niet zeker weet of u niet weet, kunt u het beste de beste beslissing gebruiken.

4. Als het filter werd genegeerd vanwege beleidsregels bij het verzenden, ziet u informatie over dat beleid.

   Als het filter niet door een of meer beleidsregels werd genegeerd, wordt de scan over enkele minuten voltooid. Als u op de koppeling naar de status klikt, ziet u aanvullende informatie over de verzending. Dit omvat de resultaten van de beleidscontrole en de rescan-Verdict. Opmerking Hiermee wordt de e-mail niet uitgevoerd via de Office 365 ATP-stack voor volledig filteren, maar wordt een gedeeltelijk herscan uitgevoerd op basis van bepaalde kenmerken van de e-mail, URL of het bestand.

5. Wanneer u klaar bent, klikt u op de knop **verzenden** .

![Voorbeeld van URL-indiening](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Een verdachte URL naar Microsoft verzenden

1. Selecteer in de sectie **object type** de optie **URL**. Voer in het vak dat wordt weergegeven, de volledige URL in (bijvoorbeeld <https://www.fabrikam.com/marketing.html> ).

2. Selecteer een van de volgende opties in de sectie **reden voor indiening** .

   - **Mag niet zijn geblokkeerd**

   - **Moet zijn geblokkeerd**: Selecteer **phishing** of **malware**.

3. Wanneer u klaar bent, klikt u op de knop **verzenden** .

![Voorbeeld van e-mail verzending](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Een verdacht bestand bij Microsoft indienen

1. Selecteer in de sectie **object type** de optie **bijlage**.

2. Klik op **bestand kiezen**. In het dialoogvenster dat wordt weergegeven, zoekt en selecteert u het bestand en klikt u vervolgens op **openen**.

3. Selecteer een van de volgende opties in de sectie **reden voor indiening** .

   - **Mag niet zijn geblokkeerd**

   - Is **geblokkeerd**: **malware** is de enige keuze en wordt automatisch geselecteerd...

4. Wanneer u klaar bent, klikt u op de knop **verzenden** .

![Voorbeeld van bijlagen verzenden](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Beheerders inzendingen weergeven

Ga in het beveiligings & compliance naar uitnodigingen voor **risicobeheer** \> **Submissions**, ga na of u het tabblad **admin-submissies** gebruikt, en klik vervolgens op **nieuwe indiening**.

Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) filteren met **id voor indienen** (een GUID-waarde die is toegewezen aan elke verzending) door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) . U kunt meerdere waarden opgeven, gescheiden door komma's.

Als u de filtercriteria wilt wijzigen, klikt u op de knop voor de **leverings-id** en kiest u een van de volgende waarden:

- **Afzender**
- **Onderwerp/URL/bestandsnaam**
- **Verzonden door**
- **Type levering**
- **Status**

![Filter opties voor beheerders inzendingen](../../media/admin-submission-email-filter-options.png)

Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** . Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.

Onder de grafiek bevinden zich drie tabbladen: **e-mail** (standaard), **URL**en **bijlage**.

### <a name="view-admin-email-submissions"></a>E-mail inzendingen van de beheerder weergeven

Selecteer het tabblad **e-mail** .

U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Einddatum**
- **Ingediende id**: een GUID-waarde die is toegewezen aan elke verzending.
- **Verzonden door**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **IP van afzender**<sup>\*</sup>
- **Type levering**
- **Bezorgings reden**
- **Status**<sup>\*</sup>
- **Typebesturingselement**
- **Besturingselementbron**

  <sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.

### <a name="view-admin-url-submissions"></a>Ingediende items van de beheerders-URL weergeven

Klik op het tabblad **URL** .

U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Einddatum**
- **Verzendings-ID**
- **Verzonden door**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Type levering**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.

### <a name="view-admin-attachment-submissions"></a>Ingediende beheerders bijlagen weergeven

Klik op het tabblad **bijlagen** .

U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Einddatum**
- **Verzendings-ID**
- **Verzonden door**<sup>\*</sup>
- **Bestandsnaam**<sup>\*</sup>
- **Type levering**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.

## <a name="view-user-submissions-to-microsoft"></a>Naar Microsoft verzonden gebruikers inzendingen weergeven

Als u de [invoegtoepassing bericht rapporteren](enable-the-report-message-add-in.md)hebt geïmplementeerd of personen de [ingebouwde rapporten gebruiken in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kunt u zien wat gebruikers rapporteren op het tabblad **gebruikers** namen.

1. Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.

2. Selecteer het tabblad **gebruikers submissies** en klik vervolgens op **nieuwe verzending**.

U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Ingediend op**
- **Verzonden door**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **IP van afzender**<sup>\*</sup>
- **Type levering**

<sup>\*</sup> Als u op deze waarde klikt, wordt er meer informatie weergegeven in een flyout.

Boven aan de pagina kunt u een begindatum, een einddatum en (standaard) u kunt filteren op **afzender** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) . U kunt meerdere waarden opgeven, gescheiden door komma's.

Als u de filtercriteria wilt wijzigen, klikt u op de knop **afzender** en kiest u een van de volgende waarden:

- **Afzenderdomein**
- **Onderwerp**
- **Verzonden door**
- **Type levering**
- **IP van afzender**

![Filter opties voor gebruikers inzendingen](../../media/user-submissions-filter-options.png)

Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** . Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Gebruikers inzendingen weergeven voor het aangepaste Postvak

Als u [een aangepast postvak hebt geconfigureerd](user-submission.md) om door de gebruiker gerapporteerde berichten te ontvangen, kunt u berichten weergeven en ook verzenden die zijn bezorgd in het rapportage postvak.

1. Ga in het beveiligings & compliance naar inzendingen van **risicobeheer** \> **Submissions**.

2. Selecteer het tabblad **aangepast postvak** .

U kunt op de knop **kolom opties** onder aan de pagina klikken om kolommen toe te voegen aan of te verwijderen uit de weergave:

- **Ingediend op**
- **Verzonden door**<sup>\*</sup>
- **Onderwerp**<sup>\*</sup>
- **Afzender**
- **IP van afzender**<sup>\*</sup>
- **Type levering**

Boven aan de pagina kunt u een begindatum, een einddatum en u kunt filteren op **ingediend** door een waarde in te voeren in het vak en op de ![ knop Vernieuwen te klikken ](../../media/scc-quarantine-refresh.png) . U kunt meerdere waarden opgeven, gescheiden door komma's.

Als u de resultaten wilt exporteren, klikt u boven aan de pagina op **exporteren** en selecteert u gegevens of **tabellen**van de **grafiek** . Sla het CSV-bestand op in het dialoogvenster dat wordt weergegeven.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Berichten indienen bij Microsoft vanuit het aangepaste Postvak

Als u het aangepaste postvak hebt geconfigureerd om door de gebruiker gerapporteerde berichten te onderscheppen zonder de berichten naar Microsoft te verzenden, kunt u specifieke berichten zoeken en naar Microsoft voor analyse verzenden. Hiermee verplaatst u een gebruiker bij het indienen van een beheerder.

Selecteer op het tabblad **aangepast postvak** een bericht in de lijst, klik op de knop **actie** en voer een van de volgende opties uit:

- **Rapport opschonen**
- **Phishing melden**
- **Malware melden**
- **Spam rapporteren**

![Opties op de actieknop](../../media/user-submission-custom-mailbox-action-button.png)
