---
title: Schakel over naar EOP van Google Postini, de Barracuda Spam and Virus Firewall of Cisco IronPort
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
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: Het doel van dit onderwerp is om u te helpen het proces te begrijpen voor het overschakelen naar Exchange Online Protection (EOP) van een on-premises e-mailhygiëneapparaat of cloudgebaseerde beveiligingsservice, en vervolgens om u te helpen bij het aan de slag gaan.
ms.openlocfilehash: e3877f8093f56a0f978ad915769334678afe26e3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810441"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Schakel over naar EOP van Google Postini, de Barracuda Spam and Virus Firewall of Cisco IronPort

 Het doel van dit onderwerp is om u te helpen het proces te begrijpen voor het overschakelen naar Exchange Online Protection (EOP) van een on-premises e-mailhygiëneapparaat of cloudgebaseerde beveiligingsservice, en vervolgens om u te helpen bij het aan de slag gaan. Er zijn veel oplossingen voor het filteren van spam, maar het proces voor het overschakelen naar EOP is in de meeste gevallen vergelijkbaar.

Als u nieuw bent bij EOP en u een overzicht van de functies wilt lezen voordat u besluit over te schakelen, begint u met het [overzichtsonderwerp Exchange Online Protection.](exchange-online-protection-overview.md)

Voordat u overstapt naar EOP, is het belangrijk om na te denken over de vraag of u uw eop-beveiligde postvakken in de cloud wilt hosten, met Exchange Online, on-premises of in een hybride scenario. (Hybride betekent dat u een aantal postvakken hebt die on-premises worden gehost en een ander gedeelte wordt gehost met Exchange Online.) Elk van deze hostingscenario's: cloud, on-premises en hybride, is mogelijk, maar de installatiestappen kunnen variëren. Hier volgen een paar overwegingen om u te helpen bij het kiezen van de juiste implementatie:

- **EOP-beveiliging met on-premises postvakken:** dit scenario is geschikt als u een bestaande e-mailhostinginfrastructuur hebt die u wilt gebruiken, of als u zakelijke vereisten hebt om postvakken on-premises te houden en u EOP wilt gebruiken als uw cloudgebaseerde e-mailbeveiliging. [Overschakelen naar EOP standalone](#switch-to-eop-standalone) beschrijft dit scenario in meer detail.

- **EOP-beveiliging met Exchange Online-postvakken**: Dit scenario is geschikt als u EOP-bescherming en al uw mailboxen in de cloud wilt ontvangen. Het kan u helpen de complexiteit te verminderen, omdat u geen on-premises berichtenservers hoeft te onderhouden. [Overschakelen naar Exchange Online](#switch-to-exchange-online) beschrijft dit scenario.

- **EOP-beveiliging met hybride postvakken**: Misschien wilt u cloudmailboxen, maar u moet postvakken voor sommige gebruikers on-premises bewaren. Kies dit scenario als u wilt dat sommige postvakken on-premises worden gehost en een ander gedeelte wordt gehost met Exchange Online. [Overschakelen naar een hybride oplossing](#switch-to-a-hybrid-solution) beschrijft dit scenario.

## <a name="switch-to-eop-standalone"></a>Overschakelen naar EOP standalone

Als u uw mailboxen momenteel op locatie host en een on-premises beveiligingstoestel of een cloudberichtenbeschermingsservice gebruikt, u overschakelen naar EOP om te profiteren van de beveiligingsfuncties en beschikbaarheid. Als u EOP wilt instellen in een zelfstandig scenario, wat betekent dat u uw postvakken op locatie host en EOP gebruikt om e-mailbescherming te bieden, u de stappen volgen die zijn beschreven in [Het instellen van uw EOP-service.](set-up-your-eop-service.md) Het onderwerp geeft een overzicht van de stappen voor het instellen van EOP-beveiliging, waaronder aanmelden, het toevoegen van uw domein en het instellen van e-mailstroom met connectoren.

## <a name="switch-to-exchange-online"></a>Overschakelen naar Exchange Online

Misschien hebt u on-premises postvakken beschermd door een on-premises toestel en wilt u naar Exchange Online-cloudgehoste postvakken en EOP-beveiliging gaan om te profiteren van Office 365-cloudberichten en beveiligingsfuncties. Om aan de slag te gaan, u zich aanmelden voor Office 365 en uw domein toevoegen. In dit scenario hoeft u geen connectors in te stellen, omdat er geen routering is naar on-premises postvakken. Begin bij [Download de nieuwste geavanceerde functies met Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) om je aan te melden en vertrouwd te raken met de functies.

Tijdens het installatieproces van Office 365 maakt u uw postvakgebruikers in de cloud.

## <a name="switch-to-a-hybrid-solution"></a>Overschakelen naar een hybride oplossing

U slechts een deel van uw postvakken naar de cloud verplaatsen vanwege zakelijke vereisten of wettelijke overwegingen. Wanneer u een hybride scenario implementeert, u postvakken naar de cloud verplaatsen zoals uw bedrijfsvereisten vereisen. Migreren naar een hybride scenario met EOP-beveiliging is ingewikkelder dan overtestappen naar een all-cloudscenario, maar Microsoft biedt volledige hybride ondersteuning en voldoende middelen om de overstap naar hybride gemakkelijker te maken.

De beste plaats om te beginnen, als u een hybride implementatie overweegt, is [hybride implementaties van Exchange Server.](https://docs.microsoft.com/exchange/exchange-hybrid) Daarnaast zijn er een paar verschillende manieren waarop u e-mail routeren in een hybride scenario die belangrijk zijn om te begrijpen. [Hybride implementaties van Transport Routing in Exchange](https://docs.microsoft.com/exchange/transport-routing) legt elk type uit, zodat u het beste routeringsscenario kiezen op basis van uw bedrijfsvereisten.

## <a name="migration-planning"></a>Migratieplanning

Wanneer u besluit over te schakelen naar EOP, moet u speciale aandacht besteden aan de volgende gebieden:

- **Aangepaste filterregels:** als u aangepaste filterregels of beleidsregels hebt om specifieke spam op te vangen, raden we u aan EOP een periode lang te proberen met de standaardinstellingen, voordat u uw regels migreert. EOP biedt spambescherming op bedrijfsniveau met de standaardinstellingen, het kan blijken dat u sommige regels niet hoeft te migreren naar EOP. Natuurlijk, als u regels hebt die specifieke aangepaste bedrijfsbeleidsregels afdwingen, u deze maken. [Regels voor e-mailstroom (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) bieden gedetailleerde instructies voor het maken van regels voor e-mailstromen in EOP.

- **IP-lijstmetjes en IP-bloklijsten:** Als u lijsten en bloklijsten per gebruiker hebt, moet u de lijsten naar EOP kopiëren als onderdeel van uw installatieproces. Zie Het [beleid voor verbindingsfilter configureren](configure-the-connection-filter-policy.md)voor meer informatie over IP-lijstmetjes en IP-bloklijsten .

- **Beveiligde communicatie:** als u een partner hebt die versleutelde berichten nodig heeft, raden we u aan dit in te stellen in het Exchange-beheercentrum. Zie Connectors instellen [voor beveiligde e-mailstroom met een partnerorganisatie](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)als u dit scenario wilt configureren.

> [!TIP]
> Wanneer u overschakelt van een on-premises toestel naar EOP, is het mogelijk om uw toestel of een server te verlaten die bedrijfsregelcontroles uitvoert. Als uw toestel bijvoorbeeld aangepaste filtering uitvoert op uitgaande e-mail en u wilt dat het dit blijft doen, u EOP configureren om e-mail rechtstreeks naar het toestel te verzenden voor extra filtering, voordat het naar het internet wordt doorgestuurd.
