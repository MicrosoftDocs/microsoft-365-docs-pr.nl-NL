---
title: Standaard veilig in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Meer informatie over de standaardinstelling veilig in Exchange Online Protection (EOP)
ms.openlocfilehash: 8db8e7af569114e5829d24d65b8eee89c9dce8c3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787971"
---
# <a name="secure-by-default-in-office-365"></a>Standaard veilig in Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

' Veilig standaard ' is een term die wordt gebruikt voor het definiëren van de standaardinstellingen die zo veilig mogelijk zijn.

De beveiliging moet echter worden gesaldeerd met productiviteit. Dit kan gelden voor de volgende taken:

- **Bruikbaarheids** functie: de instellingen zijn niet te vinden in de manier van gebruikers productiviteit.
- **Risico**: beveiliging kan belangrijke activiteiten blokkeren.
- **Verouderde instellingen**: sommige configuraties voor oudere producten en functies kunnen worden bijgehouden voor zakelijke redenen, zelfs als nieuwe, moderne instellingen zijn verbeterd.

Microsoft 365-organisaties met postvakken in Exchange Online zijn beveiligd via Exchange Online Protection (EOP). Deze bescherming omvat:

- E-mail met verdachte malware wordt automatisch in quarantaine geplaatst en geadresseerden ontvangen een melding. Zie [anti-malwarebeleid in EOP configureren](configure-anti-malware-policies.md).
- E-mailadres dat is geïdentificeerd als een hoge betrouwbaarheid, wordt volgens de actie Antispambeleid afgehandeld. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).

Zie [overzicht van Exchange Online beveiliging](exchange-online-protection-overview.md)voor meer informatie over EOP.

Aangezien Microsoft onze klanten de mogelijkheid geeft standaard te beschermen, worden sommige tenants overschreven voor malware of phishing met een hoge betrouwbaarheid niet toegepast. Deze overschrijvingen zijn:

- Lijsten met toegestane afzenders of toegestane domeinen (Antispambeleid)
- Veilige afzenders van Outlook
- Lijst met toegestane IP-adressen (verbindingen filteren)

Meer informatie over deze overschrijvingen vindt u in [lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md).

Standaard is beveiliging niet een instelling die kan worden in-of uitgeschakeld, maar de manier waarop onze filters uit het vak werken om ongewenste en ongewenste berichten uit uw postvakken te houden. De malware en de hoge betrouwbaarheid van phishingberichten worden in quarantaine geplaatst. Alleen beheerders kunnen berichten beheren die zijn gequarantined als malware of phishing via een hoge betrouwbaarheid, en kunnen ze ook fout-positieven naar Microsoft melden. Zie voor meer informatie geplaatste [berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Meer informatie over waarom we dit doen

Standaard is de geest van veilig geveiligt: de actie die u moet uitvoeren als u het bericht schadelijk wist, ook als er sprake is van een aanval. Dit is dezelfde manier die we hebben gebruikt voor malware, en nu wordt dit gedrag uitgebreid voor phishingberichten met een hoge betrouwbaarheid. Onze gegevens duiden op dat de fout positief is voor phishingberichten met een hoge betrouwbaarheid zeer laag is, en beheerders kunnen eventuele foutberichten oplossen met beheerders inzendingen. Met onze gegevens wordt ook aangegeven dat de lijsten toegestane afzenders en toegestane domeinen in Antispambeleid en veilige afzenders in Outlook te ruim zijn en meer schade te veroorzaken dan de juiste.

Als u een andere manier wilt doen: als beveiligingsservice, handelen we namens u om te voorkomen dat uw gebruikers geen compromissen hebben. Daarnaast is beveiliging standaard geen volledige overname van uw beschikbare opties voor phishingberichten met een anti-spam beleid. Hoewel u de andere beschikbare acties voor quarantaine adviseert, blijft de andere actie beschikbaar (naar map Ongewenste E-mail of omleiden naar een e-mailadres).

## <a name="exceptions"></a>Ring

Met de enige Negeer functie voor het filteren van e-mail wordt het filteren van Exchange-e-mail stroom regels (ook wel wel transport regels genoemd) toegestaan. Als u de e-mail stroom regels wilt gebruiken om het filteren te negeren, raadpleegt u [de e-mail stroom regels gebruiken om de SCL in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

U kunt alleen overschrijvingen gebruiken in de volgende scenario's:

- Malafide simulaties: gesimuleerde aanvallen kunnen u helpen gevoelige gebruikers te identificeren voordat een echte aanval uw organisatie beïnvloedt.
- Beveiligings-SecOps-postvakken: speciale postvakken die door beveiligings teams worden gebruikt om ongefilterde berichten te ontvangen (zowel goed als slecht). Teams kan vervolgens controleren of ze schadelijke inhoud bevatten.
- Filters van derden: veilig standaard is niet van toepassing als de MX-record van het domein niet verwijst naar Office 365.
- Onjuiste positieve stappen: u kunt bepaalde berichten die nog door Microsoft worden geanalyseerd, tijdelijk toestaan [via admin-inzendingen](admin-submission.md). Net als met alle overschrijvingen, is het raadzaam dat ze tijdelijk zijn.
