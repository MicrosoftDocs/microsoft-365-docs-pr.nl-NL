---
title: 'Stap 5: Prestaties van client en Microsoft 365-service optimaliseren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Configureer TCP-instellingen en Microsoft 365-services om de prestaties te verbeteren.
ms.openlocfilehash: 2db35f67ff19998b8a70742ec8fa24cb8d517c5d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631463"
---
# <a name="step-5-optimize-client-and-microsoft-365-service-performance"></a>Stap 5: Prestaties van client en Microsoft 365-service optimaliseren

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

![Fase 1-Netwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

U kunt de prestaties verbeteren door de manier aan te passen waarop het Transmission Control Protocol (TCP) werkt tussen clientapparaten en Microsoft 365-services.

Voor clientapparaten kunt u de volgende TCP-instellingen op clientapparaten wijzigen om TCP-prestaties te optimaliseren:

- [TCP-vensterschaalbaarheid](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), zodat uw clientapparaat meer gegevens kan verzenden voordat een bevestiging wordt vereist
- [Niet-actieve TCP-tijd](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), zodat het clientapparaat efficiënter kan omgaan met open verbindingen
- [Maximale TCP-segmentgrootte](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), zodat uw clientapparaat de grootste blokken gegevens in een pakket kan verzenden
- [Selectieve TCP-bevestigingen](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), zodat de ontvangen gegevens efficiënter kunnen worden bevestigd door uw clientapparaat

Zie de volgende resources voor het optimaliseren van de prestaties van Microsoft 365-services:

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [Skype voor Bedrijven Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Web App in Project Online](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

Als tussentijds controlepunt kunt u het [afsluitcriterium](networking-exit-criteria.md#crit-networking-step5) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

[Afsluitcriterium voor netwerkinfrastructuur](networking-exit-criteria.md)
