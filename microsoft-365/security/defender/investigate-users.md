---
title: Gebruikers in Microsoft 365 Defender onderzoeken
description: Gebruikers onderzoeken op een incident in het beveiligingscentrum Microsoft 365.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, identiteiten, gegevens, apparaten, apps, incident, analyseren, reactie
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572799"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Gebruikers in Microsoft 365 Defender onderzoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

Een deel van uw incidentonderzoek kan gebruikersaccounts bevatten. Begin met het tabblad **Gebruikers** voor een incident van **incidenten & waarschuwingen >** *incident* **> gebruikers**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Voorbeeld van een gebruikerspagina voor een incident":::

Als u een snel overzicht wilt krijgen van een gebruikersaccount voor het incident, selecteert u het vinkje naast de naam van de gebruikersaccount. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Voorbeeld van het overzichtsvenster van de gebruikersaccount voor een incident in het beveiligingscentrum Microsoft 365":::

> [!NOTE]
> Op de pagina Gebruiker wordt Azure Active Directory (Azure AD)-organisatie en groepen weergegeven, zodat u inzicht hebt in de groepen en machtigingen die aan een gebruiker zijn gekoppeld.

Op deze fly-outpagina kunt u informatie over gebruikersbedreiging bekijken, inclusief actuele incidenten, actieve waarschuwingen en risiconiveau, evenals blootstelling van gebruikers, accounts, apparaten en meer.

Bovendien kunt u rechtstreeks actie ondernemen in het beveiligingscentrum Microsoft 365 om een gecompromitteerde gebruiker aan te spreken, te bevestigen dat de gebruiker is gecompromitteerd of dat deze opnieuw moet worden aangemeld.

Vanaf hier kunt u **Ga naar gebruikerspagina** selecteren om de details van een gebruikersaccount te bekijken. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Voorbeeld van de gebruikersaccountpagina voor een incident in het beveiligingscentrum Microsoft 365":::

U kunt deze pagina ook bekijken door de naam van het gebruikersaccount te selecteren in de lijst op de pagina **Gebruikers.**

De gebruikerspagina van het beveiligingscentrum Microsoft 365 combineert informatie van Microsoft Defender voor eindpunt, Microsoft Defender voor identiteit en Microsoft Cloud App Security (afhankelijk van welke licenties u hebt). 

Op deze pagina vindt u informatie die specifiek is voor het beveiligingsrisico van een gebruikersaccount. Dit omvat een score die helpt bij het beoordelen van risico's en recente gebeurtenissen en waarschuwingen die hebben bijgedragen aan het algehele risico van de gebruiker.

Vanaf deze pagina kunt u deze aanvullende acties uitvoeren: 

- Het gebruikersaccount markeren als gecompromitteerd
- Vereisen dat de gebruiker zich opnieuw aanmeldt
- Het gebruikersaccount opschorten
- De instellingen van het gebruikersaccount van Azure Active Directory (Azure AD) bekijken
- De bestanden weergeven die eigendom zijn van het gebruikersaccount
- Bestanden weergeven die met deze gebruiker zijn gedeeld. 

Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Voorbeeld van de acties op een gebruikersaccount voor een incident in het beveiligingscentrum Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Volgende stappen

Als dat nodig is voor incidenten in het proces, gaat u verder met uw [onderzoek.](investigate-incidents.md)

## <a name="see-also"></a>Zie ook

- [Overzicht incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)