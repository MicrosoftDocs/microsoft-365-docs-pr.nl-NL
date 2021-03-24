---
title: Standaard beveiligen in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Meer informatie over de standaardinstelling voor beveiliging in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f1b495a9c985077dfc88d1da7a221bb60ca10df9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060054"
---
# <a name="secure-by-default-in-office-365"></a>Standaard beveiligen in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

'Standaard beveiligd' is een term die wordt gebruikt om de standaardinstellingen te definiëren die zo veilig mogelijk zijn.

Beveiliging moet echter in balans zijn met productiviteit. Dit kan onder andere het uitbalanceren van de volgende gegevens omvatten:

- **Bruikbaarheid:** Instellingen mogen de productiviteit van gebruikers niet in de weg staan.
- **Risico:** Beveiliging kan belangrijke activiteiten blokkeren.
- **Oudere instellingen:** Sommige configuraties voor oudere producten en functies moeten mogelijk worden onderhouden om zakelijke redenen, zelfs als nieuwe, moderne instellingen zijn verbeterd.

Microsoft 365-organisaties met postvakken in Exchange Online worden beschermd door Exchange Online Protection (EOP). Deze beveiliging omvat:

- E-mail met verdachte malware wordt automatisch in quarantaine geplaatst en geadresseerden worden op de hoogte gesteld. Zie [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md).
- E-mail die is geïdentificeerd als phishing met veel vertrouwen, wordt verwerkt volgens de antispambeleidsactie. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).

Zie Overzicht van Exchange [Online Protection](exchange-online-protection-overview.md)voor meer informatie over EOP.

Omdat Microsoft onze klanten standaard veilig wil houden, worden sommige tenants niet toegepast op malware of phishing met veel vertrouwen. Deze overschrijven zijn:

- Lijsten met toegestane afzenders of toegestane domeinlijsten (antispambeleid)
- Veilige afzenders van Outlook
- Ip Allow List (verbindingsfiltering)

Meer informatie over deze overschrijven vindt u in Lijsten met veilige [afzenders maken.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> We zijn bezig om de actie  Bericht verplaatsen naar map Ongewenste e-mail af te zetten voor een hoge betrouwbaarheid van phishing-e-mail in het antispambeleid van EOP.  Antispambeleid dat deze actie gebruikt voor phishingberichten met veel vertrouwen, wordt geconverteerd naar **quarantainebericht.** De **actie Bericht omleiden naar e-mailadres** voor phishingberichten met veel vertrouwen wordt niet beïnvloed.

Beveiliging is standaard geen instelling die kan worden in- of uitgeschakeld, maar is de manier waarop onze filtering werkt uit het vak om potentieel gevaarlijke of ongewenste berichten uit uw postvakken te houden. Malware en phishingberichten met veel vertrouwen moeten in quarantaine worden geplaatst. Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware of phishing met veel vertrouwen, en ze kunnen ook van hier naar Microsoft onwaar positieven rapporteren. Zie Berichten en bestanden in quarantaine beheren als [beheerder in EOP](manage-quarantined-messages-and-files.md) voor meer informatie.

## <a name="more-on-why-were-doing-this"></a>Meer informatie over waarom we dit doen

De standaardinstelling van beveiliging is: we ondernemen dezelfde actie voor het bericht dat u zou ondernemen als u wist dat het bericht schadelijk was, zelfs wanneer een geconfigureerde uitzondering anders zou toestaan dat het bericht wordt bezorgd. Dit is dezelfde methode die we altijd hebben gebruikt voor malware en nu breiden we ditzelfde gedrag uit tot phishingberichten met veel vertrouwen.

Onze gegevens geven aan dat een gebruiker 30 keer meer kans heeft op een schadelijke koppeling in berichten in de map Ongewenste e-mail versus Quarantaine. Onze gegevens geven ook aan dat de fout-positieve rente (goede berichten die als slecht zijn gemarkeerd) voor phishingberichten met hoog vertrouwen zeer laag is en dat beheerders eventuele fout-positieven kunnen oplossen met beheerdersinzendingen.

We hebben ook vastgesteld dat de toegestane afzender en toegestane domeinlijsten in antispambeleid en Veilige afzenders in Outlook te breed waren en meer schade dan goed veroorzaakten.

Anders gezegd: als beveiligingsservice handelen we namens u om te voorkomen dat uw gebruikers worden gecompromitteerd. 

## <a name="exceptions"></a>Uitzonderingen

De enige overschrijven waarmee phishingberichten met veel vertrouwen kunnen worden overgeslagen, zijn Exchange-regels voor e-mailstroom (ook wel transportregels genoemd). Zie E-mailstroomregels gebruiken om de SCL in berichten in te stellen als u regels voor e-mailstroom wilt gebruiken om filteren [te omzeilen.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

U moet in de volgende scenario's alleen overschrijven gebruiken:

- Phishingsimulaties: Gesimuleerde aanvallen kunnen u helpen om kwetsbare gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.
- Beveiligings-/SecOps-postvakken: speciale postvakken die door beveiligingsteams worden gebruikt om ongefilterde berichten te ontvangen (zowel goed als slecht). Teams kan vervolgens controleren of ze schadelijke inhoud bevatten.
- Filters van derden: Secure is standaard niet van toepassing wanneer de MX-record van het domein niet naar Office 365 gaat.
- Onwaar-positieven: Mogelijk wilt u bepaalde berichten die nog steeds door Microsoft worden geanalyseerd, tijdelijk toestaan [via beheerdersinzendingen.](admin-submission.md) Net als bij alle overschrijvingen wordt aanbevolen dat deze tijdelijk zijn.
