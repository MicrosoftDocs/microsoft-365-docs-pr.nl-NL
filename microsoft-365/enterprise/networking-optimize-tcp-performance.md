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
# <a name="step-5-optimize-client-and-microsoft-365-service-performance"></a><span data-ttu-id="d5130-103">Stap 5: Prestaties van client en Microsoft 365-service optimaliseren</span><span class="sxs-lookup"><span data-stu-id="d5130-103">Step 5: Optimize client and Microsoft 365 service performance</span></span>

<span data-ttu-id="d5130-104">*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d5130-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 1-Netwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="d5130-106">U kunt de prestaties verbeteren door de manier aan te passen waarop het Transmission Control Protocol (TCP) werkt tussen clientapparaten en Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="d5130-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Microsoft 365 services.</span></span>

<span data-ttu-id="d5130-107">Voor clientapparaten kunt u de volgende TCP-instellingen op clientapparaten wijzigen om TCP-prestaties te optimaliseren:</span><span class="sxs-lookup"><span data-stu-id="d5130-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="d5130-108">[TCP-vensterschaalbaarheid](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), zodat uw clientapparaat meer gegevens kan verzenden voordat een bevestiging wordt vereist</span><span class="sxs-lookup"><span data-stu-id="d5130-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="d5130-109">[Niet-actieve TCP-tijd](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), zodat het clientapparaat efficiënter kan omgaan met open verbindingen</span><span class="sxs-lookup"><span data-stu-id="d5130-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="d5130-110">[Maximale TCP-segmentgrootte](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), zodat uw clientapparaat de grootste blokken gegevens in een pakket kan verzenden</span><span class="sxs-lookup"><span data-stu-id="d5130-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="d5130-111">[Selectieve TCP-bevestigingen](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), zodat de ontvangen gegevens efficiënter kunnen worden bevestigd door uw clientapparaat</span><span class="sxs-lookup"><span data-stu-id="d5130-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="d5130-112">Zie de volgende resources voor het optimaliseren van de prestaties van Microsoft 365-services:</span><span class="sxs-lookup"><span data-stu-id="d5130-112">For Microsoft 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="d5130-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d5130-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="d5130-114">Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="d5130-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="d5130-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d5130-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="d5130-116">Project Web App in Project Online</span><span class="sxs-lookup"><span data-stu-id="d5130-116">Project Web App in Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="d5130-117">Als tussentijds controlepunt kunt u het [afsluitcriterium](networking-exit-criteria.md#crit-networking-step5) voor deze stap bekijken.</span><span class="sxs-lookup"><span data-stu-id="d5130-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d5130-118">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d5130-118">Next step</span></span>

[<span data-ttu-id="d5130-119">Afsluitcriterium voor netwerkinfrastructuur</span><span class="sxs-lookup"><span data-stu-id="d5130-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
