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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u kunt overstappen op Exchange Online Protection (EOP) via een on-premises e-mail bewerkings toestel of een Cloud beveiligingsservice.
ms.openlocfilehash: a6405411a130abf8369b312f553060caf0bf3855
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827795"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Overschakelen naar EOP uit Google Postini, de Barracuda Spam en Virus Firewall of Cisco IronPort

 In dit onderwerp wordt uitgelegd hoe u overstapt op Exchange Online Protection (EOP) van een on-premises e-mail bewerkings toestel of een cloudservice op basis van een on-premises beveiliging, en om u hulpbronnen te bieden om aan de slag te gaan. Er zijn veel oplossingen voor spam filteren, maar het proces voor het overschakelen naar EOP is in de meeste gevallen vergelijkbaar.

Als u nog geen ervaring hebt met EOP en een overzicht van de functies wilt lezen voordat u gaat overstappen, begint u met het onderwerp [Exchange Online Protection Overview](exchange-online-protection-overview.md) .

Voordat u overstapt op EOP, is het belangrijk om na te denken over het feit of u in de Cloud beveiligde postvakken van EOP wilt hosten met Exchange Online, on-premises of een hybride scenario. (Hybridet betekent dat u bepaalde postvakken lokaal host, en een ander deel dat host is voor Exchange Online.) Elk van deze hosting scenario's: Cloud, on-premises en hybride, is mogelijk, maar de instellingsstappen kunnen variëren. Hier volgen enkele aandachtspunten om u te helpen bij het kiezen van de juiste implementatie:

- **EOP-bescherming met on-premises postvakken**: dit scenario is geschikt als u beschikt over een bestaande e-mail hosting-infrastructuur die u wilt gebruiken, of als u beschikt over de vereisten om de postvakken on-premises te houden en EOP wilt gebruiken als uw e-mail beveiliging op basis van de Cloud. [Overschakelen naar EOP standalone](#switch-to-eop-standalone) beschrijving dit scenario in meer detail.

- **EOP-bescherming met Exchange Online-postvakken**: dit scenario is geschikt als u EOP-beveiliging en alle postvakken die worden gehost in de Cloud. Met deze functie kunt u de complexiteit verminderen, omdat u on-premises berichtenservers niet hoeft te onderhouden. [Ga naar Exchange Online om](#switch-to-exchange-online) dit scenario te beschrijven.

- **EOP-bescherming met hybride postvakken**: wellicht wilt u Cloud postvakken gebruiken, maar u moet postvakken voor sommige gebruikers on-premises bewaren. Kies dit scenario als u wilt dat sommige postvakken lokaal worden gehost en een ander onderdeel dat wordt gehost met Exchange Online. [Als u overstapt op een hybride oplossing](#switch-to-a-hybrid-solution) , wordt dit scenario beschreven.

## <a name="switch-to-eop-standalone"></a>Overschakelen naar EOP standalone

Als u uw postvakken momenteel on-premises beheert en een on-premises beveiligings toestel of een service voor Cloud berichten beveiliging gebruikt, kunt u overstappen op EOP om te profiteren van de beschermingsfuncties en de beschikbaarheid. Als u EOP wilt instellen in een zelfstandig scenario, wat betekent dat u uw postvakken on-premises host en EOP kunt gebruiken om e-mail beveiliging te geven, kunt u de stappen volgen die worden beschreven in [uw EOP-service instellen](set-up-your-eop-service.md). In dit onderwerp worden de stappen beschreven voor het instellen van EOP-bescherming, waaronder registreren, het toevoegen van uw domein en het instellen van e-mail stromen met connectors.

## <a name="switch-to-exchange-online"></a>Overstappen op Exchange Online

Misschien hebt u on-premises postvakken beveiligd via een on-premises toestel en gaat u naar Postvak met gehoste postvakken van Exchange Online en EOP, zodat u gebruik kunt maken van de functies van de Cloud messaging en beveiliging van Microsoft 365. Als u wilt beginnen, kunt u zich registreren voor Microsoft 365 en uw domein toevoegen. Voor dit scenario hoeft u geen connectors in te stellen, omdat er geen routering is voor on-premises postvakken. Begin [de nieuwste geavanceerde functies met Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) om u aan te melden en maak kennis met de functies hiervan.

Tijdens het installatieproces van Microsoft 365 maakt u de Cloud gebruikers van de Cloud.

## <a name="switch-to-a-hybrid-solution"></a>Overschakelen naar een hybride oplossing

U kunt slechts een deel van uw postvakken verplaatsen naar de Cloud vanwege zakelijke vereisten of regelgeving. Wanneer u een hybride scenario implementeert, kunt u postvakken naar de Cloud verplaatsen wanneer u uw bedrijfsbehoeften dicteert. Het migreren naar een hybride scenario met EOP-bescherming is ingewikkelder dan overstappen op een scenario in de Cloud, maar Microsoft biedt volledige hybride ondersteuning en voldoende bronnen, zodat de overstap naar hybride eenvoudiger wordt.

De beste plaats om te beginnen als u een hybride implementatie gaat, is [hybride implementaties van Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid). Daarnaast zijn er een aantal manieren om e-mail te routeren in een hybride scenario dat belangrijk voor u is. [Transport routering in hybride implementaties van Exchange](https://docs.microsoft.com/exchange/transport-routing) legt elk type aan, zodat u het beste routeringsscenario kunt kiezen op basis van uw bedrijfsvereisten.

## <a name="migration-planning"></a>Migratieplanning

Als u wilt overstappen op EOP, moet u rekening houden met de volgende punten:

- **Regels voor aangepaste filtering**: als u op een aangepaste filters-of bedrijfsbeleidsregels beschikt om bepaalde spam te onderscheppen, raden we u aan EOP met de standaardinstellingen te controleren voordat u de regels migreert. EOP biedt spam bescherming op ondernemingsniveau met de standaardinstellingen, maar het is mogelijk dat u sommige regels niet hoeft te migreren naar EOP. Als u regels hebt voor het afdwingen van specifieke zakelijke beleidsregels, kunt u die natuurlijk ook maken. De [regels voor e-mail stroom (transportregels) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) biedt gedetailleerde instructies voor het maken van de regels voor e-mail stroom in EOP.

- Lijsten met **IP-adreslijsten en IP-blok lijsten**: als u toestaat dat lijsten en blokkeringslijsten van de gebruikers zijn toegestaan, kunt u de lijsten als onderdeel van het installatieproces kopiëren naar EOP. Zie [het beleid voor verbindings filters configureren](configure-the-connection-filter-policy.md)voor meer informatie over de lijst met IP-blok lijsten en IP-blok lijsten.

- **Beveiligde communicatie**: als u een partner hebt die versleutelde berichten vereist, dan is het raadzaam om dit in het Exchange-Beheercentrum in te stellen. Voor het configureren van dit scenario, Zie [connectors instellen voor de veilige e-mail stroom met een partnerorganisatie](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> Wanneer u overstapt van een on-premises toestel naar EOP, is het mogelijk om uw toestel of een server te verlaten, zodat de controles voor bedrijfsregels worden uitgevoerd. Als uw toestel bijvoorbeeld aangepaste filters voor uitgaande e-mail uitvoert en u dit wilt voortzetten, kunt u instellen dat EOP rechtstreeks naar het toestel verzendt voor extra filters, voordat het wordt gerouteerd naar het internet.
