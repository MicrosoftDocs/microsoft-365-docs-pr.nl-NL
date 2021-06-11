---
title: Controle door beheerder voor gerapporteerde berichten
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
description: Informatie over het controleren van berichten die worden gerapporteerd en feedback geven aan uw gebruikers.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9e6969b6dee38135ee2d1d41bbcdb2561943d1fe
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878710"
---
# <a name="admin-review-for-reported-messages"></a>Controle door beheerder voor gerapporteerde berichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> De informatie in dit artikel heeft betrekking op een voorbeeldproduct dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt uitgebracht. Dit document is alleen beschikbaar voor evaluatie- en verkenningsdoeleinden.

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met Exchange Online postvakken en Microsoft Defender voor Office 365, kunnen beheerders nu sjablonenberichten terugsturen naar eindgebruikers nadat ze gerapporteerde berichten hebben beoordeeld. Dit kan worden aangepast voor uw organisatie en op basis van de uitspraak van uw beheerder.

Deze functie is ontworpen om feedback te geven aan uw gebruikers, maar wijzigt de uitspraken van berichten in het systeem niet. Als u Microsoft wilt helpen bij het bijwerken en verbeteren van de filters, moet u berichten verzenden voor analyse met [beheerdersinzending.](admin-submission.md)

U kunt alleen gebruikers van controleresultaten markeren en op de hoogte stellen als het bericht is gerapporteerd als een onwaar positief of [onwaar negatief.](report-false-positives-and-false-negatives.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?


- U opent het Microsoft 365 beveiligingscentrum op <https://security.microsoft.com/> . Als u rechtstreeks naar de pagina **Inzendingen wilt** gaan, gebruikt u <https://security.microsoft.com/reportsubmission> .

- Als u de configuratie voor gebruikersinzendingen wilt wijzigen, moet u lid zijn van een van de volgende rollengroepen:
  - Organisatiebeheer of Beveiligingsbeheerder in het [Microsoft 365 beveiligingscentrum.](permissions-microsoft-365-security-center.md)
  - Organisatiebeheer in [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)


- U hebt ook toegang nodig tot de Exchange Online PowerShell. Als het account dat u probeert te gebruiken geen toegang heeft tot Exchange Online PowerShell, krijgt u een foutmelding met de vermelding Een e-mailadres *opgeven in uw domein.* Zie de volgende onderwerpen voor meer informatie over het in- of uitschakelen van toegang tot Exchange Online PowerShell:
  - [Toegang tot powershell in- Exchange Online uitschakelen](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Clienttoegangsregels in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>De berichten configureren die worden gebruikt om gebruikers op de hoogte te stellen

1. Ga in Microsoft 365 Defender-portal naar **E-mailbeleid** & samenwerkingsbeleid & regels Bedreigingsbeleid Anderen sectie \>  \>  \>  \> **Gebruiker gerapporteerde berichtinstellingen.**

2. Als  u op de pagina Gebruikersinzendingen de weergavenaam van de afzender wilt opgeven, gaat u  naar Het **Office 365 e-mailadres** opgeven dat u wilt gebruiken als afzender onder de sectie E-mailmeldingen voor beheerdersbeoordelingsresultaten en voert u de naam in die u wilt gebruiken. Dit is het e-mailadres dat zichtbaar is in Outlook waar de antwoorden naartoe gaan.

3. Als u een van de sjablonen wilt aanpassen, klikt u **op E-mailmelding aanpassen.** In deze flyout kunt u alleen de volgende opties aanpassen:
    - Phishing
    - Ongewenste e-mail
    - Geen bedreigingen gevonden
    - Bewustmakingstraining
    - Voettekst

4. Klik op **Opslaan** wanneer u gereed bent. Als u deze waarden wilt verwijderen, klikt **u op Verwijderen** op de pagina Gebruikersinzendingen.
