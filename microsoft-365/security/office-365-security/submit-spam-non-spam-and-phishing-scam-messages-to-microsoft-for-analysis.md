---
title: Berichten handmatig indienen bij Microsoft voor analyse
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
description: Beheerders en eindgebruikers kunnen leren hoe ze e-mailberichten (goede e-mail die als slechte of slechte e-mail is toegestaan) naar Microsoft kunnen verzenden voor analyse.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0d48c3c6f6d082085390d6e246a088b6d3f6bf0
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105546"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Berichten handmatig indienen bij Microsoft voor analyse

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Als u een beheerder bent in een organisatie met Exchange Online postvakken,  raden we u aan de pagina Inzendingen te gebruiken in de Microsoft 365 Defender portal. Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.

Het kan frustrerend zijn als gebruikers in uw organisatie ongewenste e-mailberichten (spam) of phishingberichten ontvangen in hun Postvak IN of als ze geen legitiem e-mailbericht ontvangen omdat het is gemarkeerd als ongewenste e-mail. We passen onze spamfilters voortdurend aan om nauwkeuriger te zijn.

U en uw gebruikers kunnen dit proces helpen door false positives (goede e-mail gemarkeerd als slecht), onwaar negatieven (slechte e-mail toegestaan) en phishingberichten bij Microsoft in te dienen voor analyse.

> [!NOTE]
> Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle aanvragen voor analyse beantwoorden.

## <a name="submit-false-negatives-to-microsoft"></a>Onwaar negatieven indienen bij Microsoft

> [!TIP]
> Gebruikers in Outlook en webversie van Outlook (voorheen bekend als Outlook Web App) kunnen niet de volgende procedures gebruiken om onwaar negatieven te melden. Zie De invoeging Rapportbericht [inschakelen](enable-the-report-message-add-in.md) en De invoeging Phishing melden inschakelen voor meer informatie over het installeren en gebruiken van [deze hulpprogramma's.](enable-the-report-phish-add-in.md)

Als u een bericht ontvangt dat spamfilters heeft ontvangen die als spam of phishing hadden moeten worden geïdentificeerd, kunt u het bericht indien nodig indienen bij de teams Microsoft Spam Analysis en Microsoft Phishing Analysis. De analisten bekijken het bericht en voegen het toe aan de filters voor de hele service als het voldoet aan de classificatiecriteria.

1. Maak een nieuw, leeg e-mailbericht met een van de volgende geadresseerden:

   - **Ongewenste e-mail**: `junk@office365.microsoft.com`
   - **Phishing**: `phish@office365.microsoft.com`

2. Sleep en drop het ongewenste e-mailbericht of phishingbericht naar het nieuwe bericht. Hiermee wordt het ongewenste e-mailbericht of phishingbericht op opslaan als bijlage in het nieuwe bericht. Kopieer en plak de inhoud van het bericht niet of doorsturen (we hebben het oorspronkelijke bericht nodig, zodat we de berichtkoppen kunnen controleren).

   > [!NOTE]
   >
   > - U kunt meerdere berichten in het nieuwe bericht bij elkaar brengen. Zorg ervoor dat alle berichten hetzelfde type zijn: phishingberichten of ongewenste e-mailberichten.
   > - Laat de body van het nieuwe bericht leeg.
   > - Gebruik de indeling .msg (standaardindeling Outlook)of .eml (standaardinstelling Outlook webnotatie) voor de bijgevoegde berichten.

3. Wanneer u klaar bent, klikt u op **Verzenden.**

> [!TIP]
> Beheerders kunnen op verschillende manieren specifieke berichten blokkeren die verkeerd worden geïdentificeerd als spam. Zie Geblokkeerde afzenderlijsten maken in EOP voor [meer informatie.](create-block-sender-lists-in-office-365.md)

## <a name="submit-false-positives-to-microsoft"></a>Fout-positieven indienen bij Microsoft

> [!TIP]
> In plaats van de volgende procedures te gebruiken voor het rapporteren van fout-positieven, kunnen gebruikers in Outlook en webversie van Outlook de invoegvoeging Rapportbericht of de invoeging Phishing melden gebruiken. Zie De invoeging Rapportbericht [inschakelen](enable-the-report-message-add-in.md) en De invoeging Phishing melden inschakelen voor meer informatie over het installeren en gebruiken van [deze hulpprogramma's.](enable-the-report-phish-add-in.md)

Als een bericht onjuist is geïdentificeerd als spam, kunt u het bericht indienen bij het Microsoft Spam Analysis Team. De analisten evalueren het bericht en (afhankelijk van de resultaten van de analyse) de filters voor de hele service kunnen worden aangepast om het bericht door te sturen.

1. Maak een nieuw, leeg e-mailbericht met `not_junk@office365.microsoft.com` als geadresseerde.

2. Sleep en zet het verkeerd geïdentificeerde bericht in het nieuwe bericht. Hiermee wordt het verkeerd geïdentificeerde bericht op opslaan als bijlage in het nieuwe bericht. Kopieer en plak de inhoud van het bericht niet of doorsturen (we hebben het oorspronkelijke bericht nodig, zodat we de berichtkoppen kunnen controleren).

   > [!NOTE]
   >
   > - U kunt meerdere berichten in het nieuwe bericht bij elkaar brengen. Zorg ervoor dat alle berichten hetzelfde type zijn: phishingberichten of ongewenste e-mailberichten.
   > - Laat de body van het nieuwe bericht leeg.
   > - Gebruik de indeling .msg (standaardindeling Outlook)of .eml (standaardinstelling Outlook webnotatie) voor de bijgevoegde berichten.

3. Wanneer u klaar bent, klikt u op **Verzenden.**

> [!TIP]
> Beheerders kunnen op verschillende manieren toestaan dat specifieke berichten spamfilters overslaan. Zie Lijsten met veilige afzenders maken in EOP voor [meer informatie.](create-safe-sender-lists-in-office-365.md)

## <a name="where-is-the-data-from-submissions-to-microsoft-stored"></a>Waar worden de gegevens uit inzendingen naar Microsoft opgeslagen?

De gegevens bevinden zich in de Office 365 compliancegrens in Noord-Amerikaanse datacenters. De gegevens worden beoordeeld door analisten van het technische team om de effectiviteit van de filters te verbeteren.

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Een e-mailstroomregel maken om kopieën te ontvangen van berichten die worden gerapporteerd aan Microsoft

Zie Regels voor [e-mailstroom gebruiken voor](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)instructies om te zien wat gebruikers rapporteren aan Microsoft.
