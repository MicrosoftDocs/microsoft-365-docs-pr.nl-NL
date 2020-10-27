---
title: ServiceNow tickets maken en bijhouden in het Microsoft 365-Beveiligingscentrum
description: Informatie over het maken en bijhouden van tickets in ServiceNow vanuit het Microsoft 365 Beveiligingscentrum.
keywords: beveiliging, Microsoft 365, M365, Secure Score, beveiliging centrum, ServiceNow, tickets, taken
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
ms.openlocfilehash: 8992efdd79295b6b56b8f033bd97b10f59a7a4d5
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769673"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>ServiceNow tickets maken en bijhouden in het Microsoft 365-Beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
>**De voorbeeldperiode voor de ServiceNow-connector eindigt**<br>
>Deze functie is niet meer beschikbaar voor het einde van november 2020. Bedankt voor uw feedback en voortdurende ondersteuning terwijl we volgende stappen bepalen.

Het [Microsoft 365 Beveiligingscentrum](overview-security-center.md) is verbeterd met de mogelijkheid voor het zelf maken en bijhouden van tickets in ServiceNow. [Meer informatie over ServiceNow](https://www.servicenow.com/)

In het Beveiligingscentrum kunnen beveiligingsbeheerders rechtstreeks een actie ondernemen voor het oplossen van beveiligings punten voor [Microsoft](microsoft-secure-score.md) voor ServiceNow en een ticket maken. Beide ticket beheer en het wijzigen van beheer tickets kunnen worden gemaakt. Spoor tickets in de startpagina van het Beveiligingscentrum en in ServiceNow.

- [**Meer informatie over vereisten, gegevensuitwisseling en probleemoplossing**](tickets.md)
- **ServiceNow tickets beheren in het compliance Center** (niet beschikbaar)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Microsoft 365-Beveiligingscentrum verbinden met ServiceNow

Ga naar de startpagina van het Microsoft 365-Beveiligingscentrum om de ServiceNow-verbindings kaart weer te geven.

![Gebruikt u ServiceNow](../../media/do-you-use-servicenow-250.png)

Selecteer "verbinding maken met ServiceNow" om naar de instellingenpagina van ServiceNow te gaan. Volg de instructies om de Microsoft 365 connector-app te machtigen.

> [!NOTE]
> Voordat u de verbinding tussen Microsoft 365 Beveiligingscentrum en ServiceNow machtigt, moet u ervoor zorgen dat u de aanmeldingsgegevens van gebruikers en wachtwoorden van de gebruikers die u in de installatiestappen hebt gemaakt, gebruikt. Gebruik geen persoonlijke referenties.

Nadat u de instructies hebt gevolgd en de verbinding hebt geautoriseerd, bekijkt u de status van de verbinding op de verbinding van het Microsoft 365-Beveiligingscentrum en in de ServiceNow Microsoft 365 ticketing connector app Experience. U bent nu klaar om taken te maken.

### <a name="troubleshooting"></a>Problemen oplossen

Veelvoorkomende fouten bij het maken van een verbindingsprocedure en de manier waarop u deze problemen kunt oplossen, vindt u in de [sectie Probleemoplossing](tickets.md#troubleshooting).

## <a name="create-a-task-and-share-it-to-servicenow"></a>Een taak maken en delen in ServiceNow

Wanneer de integratie is geconfigureerd, maakt u ServiceNow taken op basis van specifieke acties van [Microsoft Secure scores](microsoft-secure-score.md) . Ga naar het Microsoft 365-Beveiligingscentrum en selecteer **delen** . Een van de opties voor vervolgkeuzelijsten is ServiceNow.

Er wordt een taak gegenereerd waarbij u de prioriteit kunt instellen en de naam, de beschrijving of de vervaldatum kunt wijzigen. Wanneer alle verplichte velden zijn ingevuld, verzendt u de taak naar ServiceNow.

De taak wordt weergegeven in ServiceNow als een aanvraag voor het wijzigen van de beveiligings-en configuratie van Microsoft 365.

## <a name="track-tickets"></a>Tickets bijhouden

Wanneer ServiceNow-en ticket beheer tickets zijn gemaakt, worden deze weergegeven op kaarten op de startpagina van het Microsoft 365-Beveiligingscentrum. Met deze kaarten kunt u een ticket maken, alle tickets weergeven of de ServiceNow-configuratie beheren.

![ServiceNow tickets voor wijzigingsbeheer](../../media/change-management-375.png)  ![ServiceNow-tickets voor incidentbeheer](../../media/incident-management-375.png)

Als u uw ServiceNow-integratie wilt in het Microsoft 365-Beveiligingscentrum wilt inrichten of beheren, selecteert u **ServiceNow-configuratie beheren** op een van de kaarten. Vervolgens verwijdert u de huidige ServiceNow-verbinding en wijzigt u de namen van ticket Staten.

Met ServiceNow-tickets die zichtbaar zijn in het Microsoft 365-Beveiligingscentrum, worden uw taken weergegeven op een plaats waar ze op uw andere beveiligings dashboarditems kunnen worden bijgehouden en afgehandeld.

## <a name="resources"></a>Resources

- [Meer informatie over vereisten, gegevensuitwisseling en probleemoplossing](tickets.md)
- [Microsoft Secure Score](microsoft-secure-score.md)
