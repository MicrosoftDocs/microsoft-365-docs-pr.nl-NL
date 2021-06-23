---
title: Fout-positieven en fout-negatieven rapporteren in Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Informatie over het rapporteren van onwaar positieven en onwaar negatieven in Outlook met de functie Rapportbericht.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 458e7d16e2614e7bac3a0aac5a4310e6353ab569
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082922"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Fout-positieven en fout-negatieven rapporteren in Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Als u een beheerder bent in een Microsoft 365 organisatie met Exchange Online postvakken, raden  we u aan de pagina Inzendingen te gebruiken in de Microsoft 365 Defender portal. Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.

In Microsoft 365 organisaties met postvakken in Exchange Online of on-premises postvakken met hybride moderne verificatie, kunt u fout-positieven (goede e-mail die is geblokkeerd of verzonden naar ongewenste map) en onwaar negatieven (ongewenste e-mail of phish die in het Postvak IN is bezorgd) indienen bij Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

- Voor de beste gebruikersinzendingservaring gebruikt u de invoeging Rapportbericht of de invoeging Phishing melden.

  > [!IMPORTANT]
  > De ingebouwde ervaring voor het melden van ongewenste e-mail of phishing in Outlook kan geen gebruik maken van het beleid voor het indienen [van gebruikers.](./user-submission.md) We raden u aan in plaats daarvan de invoeging Rapportbericht of de invoeging Phishing melden te gebruiken.

- De invoegtoepassing Rapportbericht en de invoegtoepassing Phishing melden werken voor Outlook op alle platforms (webversie van Outlook, iOS, Android en desktop).

- Als u een beheerder bent in een organisatie met Exchange Online postvakken, gebruikt u de portal Inzendingen in de Microsoft 365 Defender portal. Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.

- U kunt configureren om berichten rechtstreeks naar Microsoft te verzenden, een postvak dat u opgeeft of beide. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)

- Zie Het rapportbericht inschakelen of de phishing-invoegvoegingen rapporteren voor meer informatie over het verkrijgen en inschakelen van het rapportbericht of de [phishing-invoegvoegingen.](enable-the-report-message-add-in.md)

- Zie Berichten en bestanden rapporteren aan Microsoft voor meer informatie over het rapporteren van berichten [aan Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-report-message-feature"></a>De functie Rapportbericht gebruiken

### <a name="report-junk-and-phishing-messages"></a>Ongewenste e-mailberichten en phishingberichten rapporteren

Voor berichten in het Postvak IN of een andere e-mailmap, behalve Ongewenste e-mail, gebruikt u de volgende methode om spam- en phishingberichten te melden:

1. Selecteer de **puntjes** Meer acties in de rechterbovenhoek van het geselecteerde bericht, selecteer **Bericht** rapporteren in de vervolgkeuzelijst en selecteer vervolgens **Ongewenste** e-mail of **Phishing.**

   ![Rapportbericht - Meer acties](../../media/report-message-more-actions.png)

   ![Rapportbericht - Ongewenste e-mail en phishing](../../media/report-message-junk-phishing.png)

2. De geselecteerde berichten worden naar Microsoft verzonden voor analyse en:
   - Verplaatst naar de map Ongewenste e-mail als ze als spam zijn gerapporteerd.
   - Verwijderd als ze als phishing zijn gerapporteerd.

### <a name="report-messages-that-are-not-junk"></a>Berichten rapporteren die geen ongewenste e-mail zijn

1. Selecteer de **drie** puntjes Meer acties in de rechterbovenhoek van het geselecteerde bericht, selecteer **Bericht** rapporteren in de vervolgkeuzelijst en selecteer **vervolgens Geen ongewenste e-mail.**

   ![Rapportbericht - Meer acties](../../media/report-message-more-actions.png)

   ![Rapportbericht - Geen ongewenste e-mail](../../media/report-message-not-junk.png)

2. Het geselecteerde bericht wordt ter analyse naar Microsoft verzonden en verplaatst naar Postvak IN of een andere opgegeven map.

## <a name="view-and-review-reported-messages"></a>Gerapporteerde berichten weergeven en controleren

Als u berichten wilt bekijken die gebruikers rapporteren aan Microsoft, hebt u de volgende opties:

- Gebruik de **pagina Inzendingen** in de Microsoft 365 Defender portal. Zie Gebruikersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)
- Maak een regel voor de e-mailstroom (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden. Zie Regels voor [e-mailstroom gebruiken voor](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)instructies om te zien wat gebruikers rapporteren aan Microsoft.
