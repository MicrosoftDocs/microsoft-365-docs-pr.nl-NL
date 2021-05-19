---
title: Gebruikers onderzoeken in Microsoft 365 Defender
description: Gebruikers onderzoeken voor een incident in het Microsoft 365 beveiligingscentrum.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, monitor, rapport, identiteiten, gegevens, apparaten, apps, incident, analyseren, antwoord
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
ms.openlocfilehash: 7084b9370a0dd83265b37ff1d152e2164fe32813
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539129"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Gebruikers onderzoeken in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

Een deel van uw incidentonderzoek kan gebruikersaccounts zijn. Begin met het **tabblad Gebruikers** voor een incident van Incidenten & **waarschuwingen >** incident *>* **Gebruikers.** 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Voorbeeld van een pagina Gebruikers voor een incident":::

Als u een beknopt overzicht wilt krijgen van een gebruikersaccount voor het incident, selecteert u het vinkje naast de naam van het gebruikersaccount. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Voorbeeld van het overzichtsvenster voor gebruikersaccounts voor een incident in het Microsoft 365 beveiligingscentrum":::

> [!NOTE]
> Op de pagina Gebruiker ziet Azure Active Directory (AD)-organisatie en groepen, zodat u inzicht krijgt in de groepen en machtigingen die aan een gebruiker zijn gekoppeld.

Op deze fly-outpagina kunt u informatie over bedreigingen van gebruikers bekijken, waaronder actuele incidenten, actieve waarschuwingen en risiconiveau, evenals blootstelling van gebruikers, accounts, apparaten en meer.

Daarnaast kunt u rechtstreeks actie ondernemen in het Microsoft 365 beveiligingscentrum om een gecompromitteerde gebruiker aan te pakken, waarbij wordt bevestigd dat de gebruiker is gecompromitteerd of dat hij of zij zich opnieuw moet aanmelden.

Hier kunt u Ga naar gebruikerspagina selecteren **om** de details van een gebruikersaccount te bekijken. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Voorbeeld van de pagina gebruikersaccount voor een incident in het Microsoft 365 beveiligingscentrum":::

U kunt deze pagina ook zien door de naam van het gebruikersaccount te selecteren in de lijst op de **pagina** Gebruikers.

Op Microsoft 365 pagina van het beveiligingscentrum worden gegevens van Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit en Microsoft Cloud App Security (afhankelijk van welke licenties u hebt) gecombineerd. 

Op deze pagina ziet u informatie die specifiek is voor het beveiligingsrisico van een gebruikersaccount. Dit omvat een score die helpt bij het beoordelen van risico's en recente gebeurtenissen en waarschuwingen die hebben bijgedragen aan het algehele risico van de gebruiker.

Op deze pagina kunt u deze extra acties uitvoeren: 

- Het gebruikersaccount markeren als gecompromitteerd
- De gebruiker verplichten zich opnieuw aan te melden
- Het gebruikersaccount opschorten
- De gebruikersaccountinstellingen Azure Active Directory (Azure AD) bekijken
- De bestanden weergeven die eigendom zijn van het gebruikersaccount
- Bestanden weergeven die met deze gebruiker zijn gedeeld. 

Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Voorbeeld van de acties op een gebruikersaccount voor een incident in het Microsoft 365 beveiligingscentrum":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Volgende stappen

Ga zo nodig door met uw onderzoek als dit nodig is voor incidenten in [de procedure.](investigate-incidents.md)

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)