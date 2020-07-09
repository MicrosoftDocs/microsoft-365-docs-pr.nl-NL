---
title: ServiceNow-tickets maken en bijhouden in het Microsoft 365-beveiligingscentrum
description: Meer informatie over het maken en bijhouden van tickets in ServiceNow vanuit microsoft 365-beveiligingscentrum.
keywords: beveiliging, Microsoft 365, M365, secure score, security center, ServiceNow, tickets, taken
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 48512cf2fff802509ebaa14ca69d3ca02908902e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2020
ms.locfileid: "45087913"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>ServiceNow-tickets maken en bijhouden in het Microsoft 365-beveiligingscentrum

Het [Microsoft 365-beveiligingscentrum](overview-security-center.md) is verbeterd met de mogelijkheid om in ServiceNow native tickets te maken en bij te houden. [Meer informatie over ServiceNow](https://www.servicenow.com/)

In het beveiligingscentrum kunnen beveiligingsbeheerders een [microsoft secure score-verbeteringsactie](microsoft-secure-score.md) rechtstreeks naar ServiceNow verzenden en een ticket maken. Zowel incident management en change management tickets kunnen worden gemaakt. Ze kunnen vervolgens worden gevolgd op de startpagina van het beveiligingscentrum en ServiceNow.

- [**Meer informatie over vereisten, gegevensuitwisseling en probleemoplossing**](tickets.md)
- **ServiceNow-tickets beheren in het compliance center** (binnenkort beschikbaar)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Microsoft 365-beveiligingscentrum verbinden met ServiceNow

Navigeer naar de startpagina van het Microsoft 365-beveiligingscentrum om de ServiceNow-verbindingskaart te bekijken.

![Gebruikt u ServiceNow](../../media/do-you-use-servicenow-250.png)

Selecteer 'Verbinding maken met ServiceNow' om naar de servicenow-instellingspagina te gaan. Volg de instructies voor het autoriseren van de Microsoft 365 Connector-app.

> [!NOTE]
> Voordat u de verbinding tussen Microsoft 365-beveiligingscentrum en ServiceNow autoriseert, moet u de aanmelding en het wachtwoord van de integratiegebruiker gebruiken die u in de installatiestappen hebt gemaakt. Gebruik uw persoonlijke referenties niet.

Nadat u de aanwijzingen hebt gevolgd en de verbinding hebt geautoriseerd, bekijkt u de verbindingsstatus op zowel de verbindingspagina van microsoft 365-beveiligingscentrum als in de ServiceNow Microsoft 365 Ticketing Connector-app-ervaring. Nu bent u helemaal klaar om te beginnen met het maken van taken!

### <a name="troubleshooting"></a>Problemen oplossen

Lees algemene fouten die u in het verbindingsproces tegenkomen en hoe u deze beperken in de [sectie Probleemoplossing](tickets.md#troubleshooting).

## <a name="create-a-task-and-share-it-to-servicenow"></a>Een taak maken en delen met ServiceNow

Zodra de integratie is ingesteld, maakt u ServiceNow-taken op basis van specifieke microsoft Secure Score-verbeteringsacties. Ga naar een verbeteringsactie in Secure Score in de Microsoft 365-beveiligingscentrumportal en selecteer het pictogram 'delen'. Een van de vervolgkeuzeopties is ServiceNow.

![ServiceNow delen in Secure Score](../../media/servicenow-share.png)

Er wordt een taak gegenereerd waarin u de prioriteit instellen en de naam, beschrijving of vervaldatum bewerken. Zodra alle vereiste velden zijn ingevuld, stuurt u de taak naar ServiceNow.

De taak is zichtbaar in ServiceNow als een Microsoft 365-aanvraag voor beveiligings- en configuratiewijziging.

## <a name="track-tickets"></a>Tickets volgen

Zodra ServiceNow change management en incident management tickets zijn gemaakt, worden ze weergegeven op kaarten in de Microsoft 365 security center startpagina. Met deze kaarten u een ticket maken, alle tickets bekijken of de ServiceNow-configuratie beheren.

![ServiceNow wijzigbeheertickets](../../media/change-management-375.png)  ![ServiceNow incident management tickets](../../media/incident-management-375.png)

Als u uw ServiceNow-integratie in het Microsoft 365-beveiligingscentrum opnieuw wilt inrichten of beheren, selecteert u **ServiceNow-configuratie beheren** op een van de kaarten. Verwijder van daaruit de huidige ServiceNow-verbinding en pas de namen van de ticketstatus aan.

Met ServiceNow-tickets die zichtbaar zijn in het Microsoft 365-beveiligingscentrum, wonen uw taken op een plaats waar ze kunnen worden gevolgd en waarop, naast uw andere beveiligingsdashboarditems, kan worden gereageerd.

## <a name="resources"></a>Resources

- [Meer informatie over vereisten, gegevensuitwisseling en probleemoplossing](tickets.md)
- [Microsoft Secure Score](microsoft-secure-score.md)