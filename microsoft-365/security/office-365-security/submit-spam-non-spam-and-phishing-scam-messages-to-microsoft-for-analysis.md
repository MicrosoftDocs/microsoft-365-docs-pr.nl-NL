---
title: Berichten handmatig naar Microsoft verzenden voor analyse
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Beheerders en eindgebruikers kunnen voor analyse leren hoe ze e-mailberichten (goede e-mailberichten die als slecht of slecht zijn gemarkeerd) kunnen verzenden naar Microsoft.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98964d17c41222fa708bdf0059c0e67151582ef1
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290367"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Berichten handmatig naar Microsoft verzenden voor analyse

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het & compliancecentrum. Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.

Dit kan frustrerend zijn wanneer gebruikers in uw organisatie ongewenste e-mail (spam) of phishingberichten in hun Postvak IN ontvangen of als ze geen legitiem e-mailbericht ontvangen omdat het als ongewenste e-mail is gemarkeerd. We zijn voortdurend bezig onze spamfilters nauwkeuriger aan te passen.

U en uw gebruikers kunnen dit proces helpen door fout-positieven (goede e-mail gemarkeerd als slecht), fout-negatieven (slechte e-mail toegestaan) en phishingberichten naar Microsoft te verzenden voor analyse.

> [!NOTE]
> Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle aanvragen voor analyse beantwoorden.

## <a name="submit-false-negatives-to-microsoft"></a>Fout-negatieven indienen bij Microsoft

> [!TIP]
> In plaats van de volgende procedures te gebruiken voor het rapporteren van fout-negatieven, kunnen gebruikers in outlook en de webversie van Outlook (voorheen Outlook Web App) de invoegversie Bericht rapporteren of Phishing melden gebruiken. Voor meer informatie over het installeren en gebruiken van deze hulpprogramma's, zie De invoegapp Bericht rapporteren inschakelen en De [phishing-invoegapp](enable-the-report-message-add-in.md) voor het melden [inschakelen.](enable-the-report-phish-add-in.md)

Als u een bericht ontvangt dat is gefilterd door spamfilters die moeten zijn aangemerkt als spam of phishing, kunt u het bericht verzenden naar de teams Microsoft Spam-analyse en Microsoft Phishing-analyse. De analisten zullen het bericht beoordelen en toevoegen aan de filters voor de hele service als het aan de classificatiecriteria voldoet.

1. Maak een nieuw, leeg e-mailbericht met een van de volgende geadresseerden:

   - **Ongewenste e-mail:**`junk@office365.microsoft.com`

   - **Phishing:**`phish@office365.microsoft.com`

2. Sleep de ongewenste e-mail of het phishingbericht naar het nieuwe bericht. Het ongewenste e-mail- of phishingbericht wordt dan als bijlage in het nieuwe bericht op slaan. Kopieer en plak de inhoud van het bericht niet of doorsturen (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen controleren).

   > [!NOTE]
   >
   > - U kunt meerdere berichten aan het nieuwe bericht koppelen. Zorg ervoor dat alle berichten van hetzelfde type zijn: phishing-berichten of ongewenste e-mailberichten.
   >
   > - Laat de tekst van het nieuwe bericht leeg.
   >
   > - Gebruik de indeling .msg (standaard Outlook-indeling) of EML-indeling (standaardindeling in de webversie van Outlook) voor de bijgevoegde berichten.

3. Klik op Verzenden wanneer u **klaar bent.**

> [!TIP]
> Beheerders kunnen op verschillende manieren specifieke berichten blokkeren die verkeerd worden aangemerkt als spam. Zie Lijsten met geblokkeerde afzenders maken [in EOP voor meer informatie.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Fout-positieven indienen bij Microsoft

> [!TIP]
> In plaats van de volgende procedures te gebruiken om fout-positieven te melden, kunnen gebruikers in outlook en de webversie van Outlook (voorheen Outlook Web App) de invoegversie Bericht rapporteren of Phishing melden gebruiken. Voor meer informatie over het installeren en gebruiken van deze hulpprogramma's, zie De invoegapp Bericht rapporteren inschakelen en De [phishing-invoegapp](enable-the-report-message-add-in.md) voor het melden [inschakelen.](enable-the-report-phish-add-in.md)


Als een bericht ten onrechte als spam is aangemerkt, kunt u het verzenden naar het Microsoft-team voor spamanalyse. De analisten zullen het bericht evalueren en (afhankelijk van de resultaten van de analyse) de filters voor de hele service kunnen worden aangepast om het bericht door te sturen.

1. Maak een nieuw, leeg e-mailbericht met `not_junk@office365.microsoft.com` als geadresseerde:

2. Sleep het verkeerd geïdentificeerde bericht naar het nieuwe bericht. Hierdoor wordt het verkeerd geïdentificeerde bericht als bijlage in het nieuwe bericht op slaan. Kopieer en plak de inhoud van het bericht niet of doorsturen (we hebben het oorspronkelijke bericht nodig zodat we de berichtkoppen kunnen controleren).

   > [!NOTE]
   >
   > - U kunt meerdere berichten aan het nieuwe bericht koppelen. Zorg ervoor dat alle berichten van hetzelfde type zijn: phishing-berichten of ongewenste e-mailberichten.
   >
   > - Laat de tekst van het nieuwe bericht leeg.
   >
   > - Gebruik de indeling .msg (standaard Outlook-indeling) of EML-indeling (standaardindeling in de webversie van Outlook) voor de bijgevoegde berichten.

3. Klik op Verzenden wanneer u **klaar bent.**

> [!TIP]
> Beheerders hebben verschillende manieren om toe te staan dat specifieke berichten spamfilters overslaan. Zie Lijsten met veilige [afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie.

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Waar worden de gegevens van inzendingen bij Microsoft opgeslagen?

De gegevens bevinden zich in de nalevingsgrens van Office 365 in het Noord-Amerikaanse datacenter. De gegevens worden beoordeeld door analisten van het technische team om de effectiviteit van de filters te helpen verbeteren.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Een regel voor de e-mailstroom maken om kopieën te ontvangen van berichten die worden gerapporteerd bij Microsoft

Zie Regels voor [e-mailstroom gebruiken om te zien wat uw gebruikers melden bij Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
