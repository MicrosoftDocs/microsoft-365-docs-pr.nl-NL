---
title: Overstappen van een andere beveiligingsservice op EOP
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
description: In dit artikel leert u hoe u overschakelt naar Exchange Online Protection (EOP) vanuit een on-premises e-mailapparaat of een cloudbeveiligingsservice.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0cb946fbb60393657aab21195bc4dd723458f16e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290187"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Overschakelen naar EOP uit Google Postini, de Barracuda Spam en Virus Firewall of Cisco IronPort

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

 Het doel van dit onderwerp is om u inzicht te geven in het proces voor het overschakelen naar Exchange Online Protection (EOP) vanuit een on-premises e-mailapparaat of een cloudbeveiligingsservice, en om u vervolgens helpbronnen te bieden om aan de slag te gaan. Er zijn veel oplossingen voor het filteren van ongewenste e-mail, maar het proces voor het overschakelen naar EOP lijkt in de meeste gevallen op elkaar.

Als u voor het eerst met EOP te maken hebt en een overzicht van de functies ervan wilt lezen voordat u besluit om over te stappen, begint u met het overzichtsonderwerp over [Exchange Online Protection.](exchange-online-protection-overview.md)

Voordat u overschakelt naar EOP, is het belangrijk na te denken of u uw met EOP beveiligde postvakken wilt hosten in de cloud, met Exchange Online, on-premises of in een hybride scenario. (Hybride betekent dat sommige postvakken on-premises worden gehost en een ander deel wordt gehost met Exchange Online.) Elk van deze hostingscenario's: cloud, on-premises en hybride versie, is mogelijk, maar de instellingsstappen kunnen variëren. Hier zijn enkele aandachtspunten om u te helpen bij het kiezen van de juiste implementatie:

- **EOP-beveiliging met on-premises** postvakken: dit scenario is geschikt als u een bestaande e-mailhostinginfrastructuur wilt gebruiken of als u zakelijke vereisten hebt om postvakken on-premises te houden en als u EOP wilt gebruiken als uw cloud-e-mailbeveiliging. [Overstappen op de zelfstandige EOP](#switch-to-eop-standalone) beschrijft dit scenario in meer detail.

- **EOP-beveiliging met Exchange** Online-postvakken: dit scenario is geschikt als u EOP-beveiliging wilt en al uw postvakken die worden gehost in de cloud. Dit kan u helpen de complexiteit te verminderen, omdat u geen on-premises berichtservers hoeft te onderhouden. [Dit scenario wordt beschreven](#switch-to-exchange-online) door over te schakelen naar Exchange Online.

- **EOP-beveiliging met hybride postvakken:** Misschien wilt u postvakken in de cloud, maar moet u voor sommige gebruikers on-premises postvakken behouden. Kies dit scenario als u wilt dat sommige postvakken on-premises worden gehost en een ander gedeelte dat wordt gehost met Exchange Online. [Overstappen op een hybride oplossing beschrijft](#switch-to-a-hybrid-solution) dit scenario.

## <a name="switch-to-eop-standalone"></a>Overschakelen naar zelfstandige EOP

Als u uw postvakken momenteel on-premises host en een apparaat voor on-premises beveiliging of een service voor cloudberichtenbeveiliging gebruikt, kunt u overstappen op EOP om te profiteren van de beveiligingsfuncties en beschikbaarheid. Als u EOP wilt instellen in een zelfstandig scenario, wat betekent dat u uw postvakken lokaal host en EOP gebruikt voor e-mailbeveiliging, kunt u de stappen volgen die worden beschreven in De [EOP-service instellen.](set-up-your-eop-service.md) In het onderwerp worden de stappen beschreven voor het instellen van EOP-beveiliging, waaronder registreren, uw domein toevoegen en het instellen van de e-mailstroom met connectors.

## <a name="switch-to-exchange-online"></a>Overstappen op Exchange Online

Misschien hebt u on-premises postvakken beveiligd door een on-premises apparaat en wilt u springen naar postvakken die in de cloud worden gehost in Exchange Online en EOP-beveiliging om gebruik te maken van de functies voor berichten- en beveiliging in de Cloud van Microsoft 365. Om aan de slag te gaan, kunt u zich registreren voor Microsoft 365 en uw domein toevoegen. In dit scenario hoeft u geen connectors in te stellen, omdat er geen routering naar on-premises postvakken is. Begin bij [De nieuwste geavanceerde functies krijgen met Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) om u aan te melden en vertrouwd te raken met de functies ervan.

Tijdens het installatieproces van Microsoft 365 maakt u uw postvakgebruikers in de cloud.

## <a name="switch-to-a-hybrid-solution"></a>Overstappen op een hybride oplossing

Mogelijk wilt u slechts een deel van uw postvakken verplaatsen naar de cloud vanwege zakelijke vereisten of wettelijke voorschriften. Wanneer u een hybride scenario implementeert, kunt u postvakken naar de cloud verplaatsen wanneer uw bedrijfsvereisten dicteren. Migreren naar een hybride scenario met EOP-beveiliging is ingewikkelder dan over te gaan op een volledig cloudscenario, maar Microsoft biedt volledige hybride ondersteuning en voldoende bronnen om de overstap naar een hybride scenario eenvoudiger te maken.

De beste plaats om te beginnen, als u een hybride implementatie overweegt, is hybride implementaties van [Exchange Server.](https://docs.microsoft.com/exchange/exchange-hybrid) Bovendien zijn er een paar verschillende manieren waarop u e-mail kunt door sturen in een hybride scenario, die belangrijk zijn om te begrijpen. [In de hybride implementaties van Exchange](https://docs.microsoft.com/exchange/transport-routing) wordt elk type uitgelegd, zodat u het beste routeringsscenario kunt kiezen, afhankelijk van uw bedrijfsvereisten.

## <a name="migration-planning"></a>Migratieplanning

Wanneer u besluit over te stappen op EOP, moet u rekening houden met de volgende punten:

- **Aangepaste filterregels:** als u aangepaste filter- of bedrijfsbeleidsregels hebt om specifieke spam te voorkomen, raden we u aan EOP een bepaalde periode met de standaardinstellingen te proberen voordat u de regels migreert. EOP biedt beveiliging tegen ongewenste e-mail op ondernemingsniveau met de standaardinstellingen. Het kan zijn dat u sommige regels niet hoeft te migreren naar EOP. Als er regels zijn die specifiek aangepast bedrijfsbeleid afdwingen, kunt u natuurlijk die regels maken. [E-mailstroomregels (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) bieden gedetailleerde instructies voor het maken van regels voor de e-mailstroom in EOP.

- **Toegestane IP-lijsten** en lijsten met IP-blokkering: als u per gebruiker toegestane lijsten en blokkeringslijsten hebt, kunt u de lijsten tijdens het installatieproces naar EOP kopiëren. Zie Het verbindingsfilterbeleid configureren voor meer informatie over de lijst met toegestane IP-adressen en de lijst met [IP-blokkeringen.](configure-the-connection-filter-policy.md)

- **Beveiligde communicatie:** als u een partner hebt die versleutelde berichten vereist, is het raadzaam dit in te stellen in het Exchange-beheercentrum. Zie Connectors instellen voor een veilige e-mailstroom met een partnerorganisatie om dit [scenario te configureren.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

> [!TIP]
> Wanneer u van een on-premises apparaat overschakelt naar EOP, is het mogelijk om uw apparaat of een server op hun plaats te laten die controles voor bedrijfsregelen uitvoert. Als uw apparaat bijvoorbeeld aangepaste filters uitvoert voor uitgaande e-mail en u dit wilt blijven doen, kunt u EOP zo configureren dat e-mail rechtstreeks naar het apparaat wordt verzonden voor extra filtering voordat deze wordt doorgestuurd naar internet.
