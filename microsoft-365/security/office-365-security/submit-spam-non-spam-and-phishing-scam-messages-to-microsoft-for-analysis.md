---
title: Berichten handmatig bij Microsoft indienen voor analyse
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Beheerders en eindgebruikers kunnen zien hoe u e-mailberichten (goede e-mailberichten die zijn gemarkeerd als beschadigd of niet toegestaan) in Microsoft voor analyse.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68a0921f85e5b916cd53ebe84e4ea7d35e39967e
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877703"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Berichten handmatig bij Microsoft indienen voor analyse

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Als u een beheerder bent van een organisatie met postvakken van Exchange Online, raden we u aan om de portal voor ingediende vragen te gebruiken in het beveiligings & nalevings centrum. Zie voor meer informatie [beheer van beheerders gebruiken om verdachte spam, phishing, url's en bestanden naar Microsoft te verzenden](admin-submission.md).

Dit kan vervelend zijn wanneer gebruikers in uw organisatie ongewenste berichten (spam) of phishingberichten in hun postvak in ontvangen, of als ze geen legitiem e-mailbericht ontvangen, omdat dit als ongewenste e-mail is gemarkeerd. Onze spamfilters worden continu nauwkeuriger afgestemd.

U en uw gebruikers kunnen dit proces helpen met het indienen van foutberichten (goede e-mailberichten die als beschadigd zijn gemarkeerd), onjuiste negatieven (onjuiste e-mail toegestaan) en phishingberichten aan Microsoft voor analyse.

> [!NOTE]
> Vanwege het grote aantal inzendingen dat we ontvangen, kunnen we mogelijk niet alle aanvragen voor analyse beantwoorden.

## <a name="submit-false-negatives-to-microsoft"></a>Onjuiste negatieven bij Microsoft indienen

> [!TIP]
> In plaats van de volgende procedures te gebruiken voor het melden van onjuiste negatieven, gebruikers in Outlook en de webversie van Outlook (voorheen Outlook Web app) kunnen de invoegtoepassing bericht rapporteren voor Microsoft Outlook gebruiken. Zie [de invoegtoepassing bericht rapporteren inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van dit hulpprogramma.

Als u een bericht ontvangt dat via spam filtert dat als spam of phishing werd herkend, kunt u het bericht naar de Microsoft spam analyse en Microsoft phishing-teams verzenden. De analisten beoordelen het bericht en voeg dit toe aan de service filters, als dit voldoet aan de classificatiecriteria.

1. Maak een nieuw, leeg e-mailbericht met een van de volgende geadresseerden:

   - **Ongewenste e-mail** : `junk@office365.microsoft.com`

   - **Phishing** : `phish@office365.microsoft.com`

2. Sleep de ongewenste e-mail of het bericht naar het nieuwe bericht. Hierdoor wordt het ongewenste e-mailbericht of het bericht opgeslagen als een bijlage in het nieuwe bericht. Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig, zodat we de berichtkoppen kunnen controleren).

   > [!NOTE]
   >
   > - U kunt meerdere berichten toevoegen aan het nieuwe bericht. Zorg ervoor dat alle berichten hetzelfde type hebben: malafide berichten of ongewenste e-mailberichten.
   >
   > - Laat de tekst van het nieuwe bericht leeg.
   >
   > - Gebruik. msg (standaardindeling van Outlook) of. eml (standaardindeling van de webversie van Outlook) voor de bijgevoegde berichten.

3. Wanneer u klaar bent, klikt u op **verzenden**.

> [!TIP]
> Beheerders hebben verschillende manieren om specifieke berichten te blokkeren die niet goed worden geïdentificeerd als spam. Zie [lijsten met geblokkeerde afzenders maken in EOP](create-block-sender-lists-in-office-365.md)voor meer informatie.

## <a name="submit-false-positives-to-microsoft"></a>Vervalste naar Microsoft verzenden

> [!TIP]
> In plaats van de volgende procedures voor het melden van foutberichten, gebruikers in Outlook en de webversie van Outlook kunnen de invoegtoepassing bericht rapporteren voor Microsoft Outlook gebruiken. Zie [de invoegtoepassing bericht rapporteren inschakelen](enable-the-report-message-add-in.md)voor informatie over het installeren en gebruiken van dit hulpprogramma.

Als een bericht onjuist is aangemerkt als ongewenste e-mail, kunt u het bericht indienen bij het team van Microsoft spam analyses. Op de analisten wordt het bericht geëvalueerd en (afhankelijk van de resultaten van de analyse) kunnen de service-Wide filters worden aangepast om het bericht toe te staan.

1. Maak een nieuw, leeg e-mailbericht met `not_junk@office365.microsoft.com` de ontvanger:

2. Sleep en zet het foutbericht in het nieuwe bericht. Hierdoor wordt het foutbericht in het nieuwe bericht opgeslagen als een bijlage. Kopieer en plak de inhoud van het bericht niet of stuur het bericht door (we hebben het oorspronkelijke bericht nodig, zodat we de berichtkoppen kunnen controleren).

   > [!NOTE]
   >
   > - U kunt meerdere berichten toevoegen aan het nieuwe bericht. Zorg ervoor dat alle berichten hetzelfde type hebben: malafide berichten of ongewenste e-mailberichten.
   >
   > - Laat de tekst van het nieuwe bericht leeg.
   >
   > - Gebruik. msg (standaardindeling van Outlook) of. eml (standaardindeling van de webversie van Outlook) voor de bijgevoegde berichten.

3. Wanneer u klaar bent, klikt u op **verzenden**.

> [!TIP]
> Beheerders hebben verschillende manieren om te voorkomen dat specifieke berichten worden gefilterd door het filteren van spam. Zie voor meer informatie [lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Een e-mail stroom regel maken om kopieën te ontvangen van berichten die bij Microsoft worden gerapporteerd

Zie voor instructies [de regels voor e-mail stroom gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
