---
title: Overschakelen naar EOP van een andere beveiligingsservice
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u overschakelt naar Exchange Online Protection (EOP) van een on-premises e-mailhygiëneapparaat of cloudbeveiligingsservice.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dfbbc44ebfed6cafb97e36b18a4fc34c91840d9b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624011"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Overschakelen naar EOP uit Google Postini, de Barracuda Spam en Virus Firewall of Cisco IronPort

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 Het doel van dit onderwerp is om u te helpen het proces te begrijpen voor het overschakelen naar Exchange Online Protection (EOP) van een on-premises e-mailhygiëneapparaat of cloudbeveiligingsservice, en u vervolgens te voorzien van helpbronnen om aan de slag te gaan. Er zijn veel spamfilteroplossingen, maar het proces voor het overschakelen naar EOP is in de meeste gevallen vergelijkbaar.

Als u nieuw bent bij EOP en u een overzicht van de functies wilt lezen voordat u besluit om over te schakelen, begint u met [het Exchange Online Protection overzichtsonderwerp.](exchange-online-protection-overview.md)

Voordat u overschakelt naar EOP, is het belangrijk na te denken of u uw EOP-beveiligde postvakken wilt hosten in de cloud, met Exchange Online, on-premises of in een hybride scenario. (Hybride betekent dat sommige postvakken on-premises worden gehost en een ander gedeelte wordt gehost met Exchange Online.) Elk van deze hostingscenario's: cloud, on-premises en hybride, is mogelijk, maar de installatiestappen kunnen variëren. Hier zijn enkele aandachtspunten om u te helpen bij het kiezen van de juiste implementatie:

- **EOP-beveiliging met on-premises** postvakken: Dit scenario is geschikt als u een bestaande e-mailhostinginfrastructuur hebt die u wilt gebruiken, of als u bedrijfsvereisten hebt om postvakken on-premises te houden en u EOP wilt gebruiken als e-mailbeveiliging in de cloud. [Overstappen op EOP standalone](#switch-to-eop-standalone) beschrijft dit scenario in meer detail.

- **EOP-beveiliging met Exchange Online** postvakken: Dit scenario is geschikt als u EOP-beveiliging en al uw postvakken wilt die in de cloud worden gehost. Het kan u helpen de complexiteit te verminderen, omdat u geen on-premises berichtenservers hoeft te onderhouden. [Overschakelen naar Exchange Online](#switch-to-exchange-online) beschrijft dit scenario.

- **EOP-beveiliging met hybride postvakken:** Misschien wilt u cloudpostvakken, maar u moet postvakken voor sommige gebruikers on-premises houden. Kies dit scenario als u wilt dat sommige postvakken on-premises worden gehost en een ander gedeelte wordt gehost met Exchange Online. [Overstappen op een hybride oplossing](#switch-to-a-hybrid-solution) beschrijft dit scenario.

## <a name="switch-to-eop-standalone"></a>Overschakelen naar zelfstandige EOP

Als u uw postvakken momenteel on-premises host en een on-premises beveiligingsapparaat of een cloudberichtenbeveiligingsservice gebruikt, kunt u overschakelen naar EOP om te profiteren van de beveiligingsfuncties en beschikbaarheid. Als u EOP wilt instellen in een zelfstandig scenario, wat betekent dat u uw postvakken on-premises host en EOP gebruikt om e-mailbeveiliging te bieden, kunt u de stappen volgen die worden beschreven in Uw [EOP-service instellen.](/exchange/standalone-eop/set-up-your-eop-service) In het onderwerp worden de stappen beschreven voor het instellen van EOP-beveiliging, zoals aanmelden, het toevoegen van uw domein en het instellen van e-mailstroom met verbindingslijnen.

## <a name="switch-to-exchange-online"></a>Overschakelen naar Exchange Online

Misschien hebt u on-premises postvakken die zijn beveiligd door een on-premises apparaat en wilt u naar Exchange Online door de cloud gehoste postvakken en EOP-beveiliging gaan om te profiteren van Microsoft 365 cloudberichten en beveiligingsfuncties. Als u wilt beginnen, kunt u zich registreren voor Microsoft 365 en uw domein toevoegen. In dit scenario hoeft u geen verbindingslijnen in te stellen, omdat er geen routering naar on-premises postvakken is. Begin bij [De nieuwste geavanceerde functies met Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) om u aan te melden en vertrouwd te raken met de functies.

Tijdens het Microsoft 365 installatieproces maakt u uw postvakgebruikers in de cloud.

## <a name="switch-to-a-hybrid-solution"></a>Overschakelen naar een hybride oplossing

Mogelijk wilt u slechts een deel van uw postvakken naar de cloud verplaatsen vanwege zakelijke vereisten of wettelijke overwegingen. Wanneer u een hybride scenario implementeert, kunt u postvakken verplaatsen naar de cloud terwijl uw zakelijke vereisten dicteren. Migreren naar een hybride scenario met EOP-beveiliging is ingewikkelder dan over te gaan op een volledig cloudscenario, maar Microsoft biedt volledige hybride ondersteuning en voldoende bronnen om de overstap naar hybride technologie gemakkelijker te maken.

De beste plek om te beginnen, als u een hybride implementatie overweegt, is Exchange Server [hybride implementaties.](/exchange/exchange-hybrid) Daarnaast zijn er een aantal verschillende manieren waarop u e-mail kunt routen in een hybride scenario die belangrijk zijn om te begrijpen. [Transportroutering in Exchange hybride implementaties](/exchange/transport-routing) legt elk type uit, zodat u het beste routeringsscenario kunt kiezen op basis van uw bedrijfsvereisten.

## <a name="migration-planning"></a>Migratieplanning

Wanneer u besluit over te schakelen naar EOP, moet u rekening houden met de volgende gebieden:

- **Aangepaste filterregels:** als u aangepaste filter- of bedrijfsbeleidsregels hebt om specifieke spam op te vangen, raden we u aan EOP te proberen met de standaardinstellingen voor een bepaalde periode voordat u de regels migreert. EOP biedt bescherming tegen spam op ondernemingsniveau met de standaardinstellingen, het kan zijn dat u bepaalde regels niet hoeft te migreren naar EOP. Als u regels hebt die specifieke aangepaste zakelijke beleidsregels afdwingen, kunt u deze natuurlijk maken. Zie Regels voor [e-mailstroom (transportregels) in](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)Exchange Online.

- **IP-lijsten en** IP-blokkeringslijsten: Als u lijsten per gebruiker toestaat en lijsten blokkeert, kunt u de lijsten als onderdeel van het installatieproces naar EOP kopiëren. Zie Het verbindingsfilterbeleid configureren voor meer informatie over de lijst met IP-toegestane en [IP-blokkeringen.](configure-the-connection-filter-policy.md)

- **Beveiligde communicatie:** als u een partner hebt die versleutelde berichten vereist, raden we u aan dit in te stellen in het Exchange beheercentrum. Zie Connectors instellen voor een veilige [e-mailstroom met een partnerorganisatie](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)om dit scenario te configureren.

> [!TIP]
> Wanneer u overschakelt van een on-premises apparaat naar EOP, is het mogelijk om uw apparaat of een server te laten staan die bedrijfsregelcontroles uitvoert. Als uw apparaat bijvoorbeeld aangepaste filtering uitvoert op uitgaande e-mail en u wilt dat dit blijft doen, kunt u EOP zo configureren dat e-mail rechtstreeks naar het apparaat wordt verzonden voor extra filtering, voordat het wordt doorgestuurd naar internet.
