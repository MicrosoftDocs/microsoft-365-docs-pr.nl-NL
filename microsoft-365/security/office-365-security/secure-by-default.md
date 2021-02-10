---
title: Standaard beveiligd in Office 365
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
description: Meer informatie over de standaardbeveiligingsinstelling in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 51b33afa6b07c040e6aa18abe996c78b770f0773
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166577"
---
# <a name="secure-by-default-in-office-365"></a>Standaard beveiligd in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Standaard beveiligd is een term die wordt gebruikt om de standaardinstellingen te definiëren die zo veilig mogelijk zijn.

Beveiliging moet echter in balans zijn met productiviteit. Dit kan onder andere zijn:

- **Bruikbaarheid:** instellingen mogen de productiviteit van gebruikers niet in de weg staan.
- **Risico:** beveiliging kan belangrijke activiteiten blokkeren.
- **Oudere instellingen:** sommige configuraties voor oudere producten en functies moeten mogelijk vanwege zakelijke redenen worden bewaard, zelfs als nieuwe, moderne instellingen zijn verbeterd.

Microsoft 365-organisaties met postvakken in Exchange Online worden beveiligd door Exchange Online Protection (EOP). Deze beveiliging omvat:

- E-mail met verdachte malware wordt automatisch in quarantaine geplaatst en geadresseerden worden op de hoogte gesteld. Zie [Antimalwarebeleid configureren in EOP.](configure-anti-malware-policies.md)
- E-mail die wordt aangemerkt als zeer vertrouwelijk phishing, wordt verwerkt volgens de actie in het antispambeleid. Zie [Antispambeleid configureren in EOP.](configure-your-spam-filter-policies.md)

Zie het overzicht van [Exchange Online Protection](exchange-online-protection-overview.md)voor meer informatie over EOP.

Omdat Microsoft onze klanten standaard beveiligd wil houden, worden sommige tenants niet toegepast op malware of phishing met hoge betrouwbaarheid. Dit zijn onder andere:

- Lijsten met toegestane afzenders of lijsten met toegestane domeinen (antispambeleid)
- Veilige afzenders in Outlook
- Lijst met toegestane IP-adressen (filteren van verbinding)

Meer informatie over deze overschrijvingen vindt u in [Lijsten met veilige afzenders maken.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> We zijn bezig de actie Bericht  verplaatsen naar map Ongewenste e-mail uit te stellen, omdat we in EOP antispambeleid e-mails met hoge vertrouwens-phishing-e-mails kunnen aanmaken.  Antispambeleid dat deze actie gebruikt om zeer vertrouwelijk phishing-berichten te gebruiken, wordt geconverteerd naar **quarantainebericht.** De **actie Bericht omleiden naar e-mailadres** voor zeer goede phishingberichten wordt niet beïnvloed.

Standaard beveiligen is geen instelling die kan worden in- of uitgeschakeld, maar is de manier waarop wordt gefilterd om mogelijk gevaarlijke of ongewenste berichten uit uw postvakken te houden. Malware en phishingberichten met hoge betrouwbaarheid moeten in quarantaine worden geplaatst. Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst als malware of phishing met een hoge betrouwbaarheid en kunnen van hier naar Microsoft ook fout-positieven rapporteren. Zie Berichten en bestanden in quarantaine beheren [als beheerder in EOP](manage-quarantined-messages-and-files.md) voor meer informatie.

## <a name="more-on-why-were-doing-this"></a>Meer informatie over waarom we dit doen

De gedachte om standaard veilig te zijn is: we voeren dezelfde actie uit op het bericht dat u zou ondernemen als u het bericht kwaadwillig zou kennen, zelfs wanneer een geconfigureerde uitzondering het bericht anders zou bezorgen. Dit is dezelfde methode die we altijd al hebben gebruikt voor malware, en nu wordt ditzelfde gedrag uitgebreid naar phishingberichten met een hoge betrouwbaarheid.

Uit onze gegevens blijkt dat een gebruiker 30 keer vaker op een schadelijke koppeling in berichten in de map Ongewenste e-mail en op Quarantaine klikt. Uit onze gegevens blijkt ook dat de fout-positieve snelheid (goede berichten gemarkeerd als slecht) voor phishingberichten met hoge betrouwbaarheid zeer laag is en dat beheerders eventuele fout-positieven kunnen oplossen met beheerdersinzendingen.

We hebben ook vastgesteld dat de toegestane afzender en toegestane domeinlijsten in antispambeleid en veilige afzenders in Outlook te ruim waren en voor meer kwaad dan goeds waren.

Om dit op een andere manier te doen: als beveiligingsservice handelen we namens u om te voorkomen dat uw gebruikers worden gehackt. 

## <a name="exceptions"></a>Uitzonderingen

Alleen Exchange-regels voor de e-mailstroom (ook wel transportregels genoemd) zijn de enige overschakeling die een zeer betrouwbaarheids-phishingbericht toestaat om filters te omzeilen. Zie Regels voor de e-mailstroom gebruiken om de SCL in berichten in te stellen als u regels voor de [e-mailstroom wilt gebruiken](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)om filters te omzeilen.

U kunt overschrijven het beste in de volgende scenario's gebruiken:

- Phishing-phishing-phishing-aanvallen: Gesimuleerde aanvallen kunnen u helpen om kwetsbaar gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.
- Beveiligings-/SecOps-postvakken: toegewezen postvakken die door beveiligingsteams worden gebruikt om niet-gefilterde berichten te krijgen (zowel goed als slecht). Teams kunnen vervolgens controleren of ze schadelijke inhoud bevatten.
- Filters van derden: Standaard is Secure niet van toepassing wanneer de MX-record van het domein niet naar Office 365 betekent.
- Fout-positieven: U wilt mogelijk tijdelijk toestaan dat bepaalde berichten die nog door Microsoft worden geanalyseerd [via beheerdersinzendingen, worden verzonden.](admin-submission.md) Net als bij alle overschrijven, wordt het aanbevolen dat deze tijdelijk zijn.
