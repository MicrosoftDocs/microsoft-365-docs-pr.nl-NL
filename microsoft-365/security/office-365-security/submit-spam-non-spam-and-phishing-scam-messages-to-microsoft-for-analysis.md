---
title: Berichten handmatig verzenden bij Microsoft voor analyse
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
description: Beheerders en eindgebruikers kunnen leren hoe ze berichten (goede e-mail gemarkeerd als slechte of slechte e-mail toegestaan) naar Microsoft voor analyse.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6973330c4504bd6478265205f60798b3b7c1875
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811036"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Berichten handmatig verzenden bij Microsoft voor analyse

> [!NOTE]
> Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Security & Compliance Center. Zie [Beheerdersinzending gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)

Het kan frustrerend zijn wanneer gebruikers in uw organisatie ongewenste berichten (spam) of phishingberichten in hun Postvak IN ontvangen of als ze geen legitiem e-mailbericht ontvangen omdat het is gemarkeerd als ongewenste e-mail. We zijn onze spamfilters voortdurend aan het finetunen om nauwkeuriger te zijn.

U en uw gebruikers kunnen dit proces helpen door valse positieven (goede e-mail gemarkeerd als slecht), valse negatieven (slechte e-mail toegestaan) en phishing-berichten aan Microsoft voor analyse.

> [!NOTE]
> Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle verzoeken om analyse beantwoorden.

## <a name="submit-false-negatives-to-microsoft"></a>Valse negatieven indienen bij Microsoft

> [!TIP]
> In plaats van de volgende procedures te gebruiken om foutieve negatieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook (voorheen Outlook Web App) de invoegtoepassing Rapportbericht voor Microsoft Outlook gebruiken. Zie [De invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van dit hulpprogramma.

Als u een bericht ontvangt dat door spamfilters is gegaan dat als spam of phishing had moeten worden geïdentificeerd, u het bericht naar gelang van het geval indienen bij de teams Microsoft Spam Analysis en Microsoft Phishing Analysis. De analisten zullen het bericht bekijken en toevoegen aan de servicebrede filters als het voldoet aan de classificatiecriteria.

1. Maak een nieuw, leeg e-mailbericht met een van de volgende ontvangers:

   - **Junk:**`junk@office365.microsoft.com`

   - **Phishing:**`phish@office365.microsoft.com`

2. Sleep en drop het ongewenste bericht of phishing in het nieuwe bericht. Hierdoor wordt het ongewenste of phishingbericht opgeslagen als bijlage in het nieuwe bericht. Kopieer en plak de inhoud van het bericht niet en verzend het bericht niet (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).

   > [!NOTE]
   > <ul><li>U meerdere berichten in het nieuwe bericht koppelen. Zorg ervoor dat alle berichten hetzelfde type zijn: phishing-scamberichten of ongewenste e-mailberichten.</li><li>Laat het lichaam van het nieuwe bericht leeg.</li><li>Gebruik de indelingen .msg (standaard Outlook-indeling) of .eml (standaard in Outlook op de webindeling) voor de bijgevoegde berichten.</li></ul>

3. Klik op **Verzenden**als u klaar bent.

> [!TIP]
> Beheerders hebben verschillende manieren om specifieke berichten te blokkeren die verkeerd worden geïdentificeerd als spam. Zie Lijsten [met geblokkeerde afzenders maken in EOP voor](create-block-sender-lists-in-office-365.md)meer informatie.

## <a name="submit-false-positives-to-microsoft"></a>Valse positieven indienen bij Microsoft

> [!TIP]
> In plaats van de volgende procedures te gebruiken om fout-positieven te melden, kunnen gebruikers in de webversie van Outlook en Outlook de invoegtoepassing Rapportbericht voor Microsoft Outlook gebruiken. Zie [De invoegtoepassing Rapportbericht inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van dit hulpprogramma.

Als een bericht onjuist is geïdentificeerd als spam, u het bericht indienen bij het Microsoft Spam Analysis Team. De analisten zullen het bericht evalueren en (afhankelijk van de resultaten van de analyse) kunnen de servicebrede filters worden aangepast om het bericht door te laten.

1. Maak een nieuw, leeg e-mailbericht met `not_junk@office365.microsoft.com` als ontvanger:

2. Sleep en drop het verkeerd geïdentificeerde bericht in het nieuwe bericht. Hiermee wordt het verkeerd geïdentificeerde bericht opgeslagen als bijlage in het nieuwe bericht. Kopieer en plak de inhoud van het bericht niet en verzend het bericht niet (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen inspecteren).

   > [!NOTE]
   > <ul><li>U meerdere berichten in het nieuwe bericht koppelen. Zorg ervoor dat alle berichten hetzelfde type zijn: phishingberichten of ongewenste e-mailberichten.</li><li>Laat het lichaam van het nieuwe bericht leeg.</li><li>Gebruik de indelingen .msg (standaard Outlook-indeling) of .eml (standaard in Outlook op de webindeling) voor de bijgevoegde berichten.</li></ul>

3. Klik op **Verzenden**als u klaar bent.

> [!TIP]
> Beheerders hebben verschillende manieren om specifieke berichten toe te staan spamfiltering over te slaan. Zie Veilige [afzenderlijsten maken in EOP voor](create-safe-sender-lists-in-office-365.md)meer informatie.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Een e-mailstroomregel maken om kopieën te ontvangen van berichten die aan Microsoft zijn gerapporteerd

Zie Regels [voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)voor instructies.
