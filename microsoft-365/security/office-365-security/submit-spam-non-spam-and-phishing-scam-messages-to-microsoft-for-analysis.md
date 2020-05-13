---
title: Berichten handmatig verzenden naar Microsoft voor analyse
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Beheerders en gebruikers kunnen leren hoe ze berichten (goede e-mail gemarkeerd als slechte of slechte e-mail toegestaan) naar Microsoft voor analyse.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed605d88f025996646c928200c20945df9c9871f
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208607"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Berichten handmatig verzenden naar Microsoft voor analyse

> [!NOTE]
> Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliance Center. Zie [Het indienen van beheerders gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)

Het kan frustrerend zijn wanneer gebruikers in uw organisatie ongewenste berichten (spam) of phishingberichten ontvangen in hun Postvak IN, of als ze geen legitiem e-mailbericht ontvangen omdat het is gemarkeerd als ongewenste e-mail. We verfijnen onze spamfilters voortdurend om nauwkeuriger te zijn.

U en uw gebruikers kunnen dit proces helpen door false positives (goede e-mail gemarkeerd als slecht), valse negatieven (slechte e-mail toegestaan) en phishing-berichten bij Microsoft in te dienen voor analyse.

> [!NOTE]
> Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle verzoeken om analyse beantwoorden.

## <a name="submit-false-negatives-to-microsoft"></a>Valse negatieven verzenden bij Microsoft

> [!TIP]
> In plaats van de volgende procedures te gebruiken om valse negatieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook (voorheen Outlook Web App) de invoegtoepassing Berichtrapport voor Microsoft Outlook gebruiken. Zie [Invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van deze tool.

Als u een bericht ontvangt dat door spamfiltering is verzonden en dat als spam of phishing had moeten worden geïdentificeerd, u het bericht naar gelang van het geval indienen bij de microsoft spamanalyse- en Microsoft Phishing-analyseteams. De analisten zullen het bericht bekijken en toevoegen aan de servicebrede filters als het voldoet aan de classificatiecriteria.

1. Maak een nieuw, leeg e-mailbericht met een van de volgende ontvangers:

   - **Junk**:`junk@office365.microsoft.com`

   - **Phishing**:`phish@office365.microsoft.com`

2. Sleep en drop de ongewenste of phishing-bericht in het nieuwe bericht. Dit zal de junk of phishing-bericht op te slaan als een bijlage in het nieuwe bericht. Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).

   > [!NOTE]
   > <ul><li>U meerdere berichten toevoegen in het nieuwe bericht. Zorg ervoor dat alle berichten hetzelfde type zijn: phishing-scamberichten of ongewenste e-mailberichten.</li><li>Laat het lichaam van het nieuwe bericht leeg.</li><li>Gebruik .msg (standaardOutlook-indeling) of .eml (standaard Outlook op de webindeling) voor de bijgevoegde berichten.</li></ul>

3. Klik op **Verzenden**als u klaar bent.

> [!TIP]
> Beheerders hebben verschillende manieren om specifieke berichten te blokkeren die verkeerd worden geïdentificeerd als spam. Zie Lijsten [met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md)voor meer informatie.

## <a name="submit-false-positives-to-microsoft"></a>Valse positieven verzenden bij Microsoft

> [!TIP]
> In plaats van de volgende procedures te gebruiken om fout-positieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook de invoegtoepassing Rapportbericht voor Microsoft Outlook gebruiken. Zie [Invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van deze tool.

Als een bericht ten onrechte is geïdentificeerd als spam, u het bericht indienen bij het Microsoft Spam Analysis Team. De analisten evalueren het bericht en (afhankelijk van de resultaten van de analyse) kunnen de servicebrede filters worden aangepast om het bericht door te laten gaan.

1. Maak een nieuw, leeg e-mailbericht met `not_junk@office365.microsoft.com` als ontvanger:

2. Sleep en laat het verkeerd geïdentificeerde bericht in het nieuwe bericht vallen. Hiermee wordt het verkeerd geïdentificeerde bericht opgeslagen als bijlage in het nieuwe bericht. Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).

   > [!NOTE]
   > <ul><li>U meerdere berichten toevoegen in het nieuwe bericht. Zorg ervoor dat alle berichten hetzelfde type zijn: phishingberichten of ongewenste e-mailberichten.</li><li>Laat het lichaam van het nieuwe bericht leeg.</li><li>Gebruik .msg (standaardOutlook-indeling) of .eml (standaard Outlook op de webindeling) voor de bijgevoegde berichten.</li></ul>

3. Klik op **Verzenden**als u klaar bent.

> [!TIP]
> Beheerders hebben verschillende manieren om specifieke berichten toe te staan spamfilters over te slaan. Zie Lijsten [met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Een e-mailstroomregel maken om kopieën te ontvangen van berichten die aan Microsoft worden gerapporteerd

Zie Regels [voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
