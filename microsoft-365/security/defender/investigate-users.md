---
title: Gebruikers analyseren in het Microsoft 365-beveiligingscentrum
description: Gebruikers analyseren in het Microsoft 365-beveiligingscentrum
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
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939728"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a>Gebruikers analyseren in het Microsoft 365-beveiligingscentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

Een deel van uw incidentanalyse kan gebruikersaccounts bevatten. Begin met het **tabblad Gebruikers** voor een incident van Incidenten & **waarschuwingen >** incident *>* **Gebruikers.** 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Voorbeeld van een pagina Gebruikers voor een incident":::

Als u een beknopt overzicht wilt krijgen van een gebruikersaccount voor het incident, selecteert u het vinkje naast de naam van het gebruikersaccount. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Voorbeeld van het overzichtsvenster voor gebruikersaccounts voor een incident in het Microsoft 365-beveiligingscentrum":::

Hier kunt u Ga naar gebruikerspagina selecteren **om** de details van een gebruikersaccount te bekijken. Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Voorbeeld van de pagina met gebruikersaccounts voor een incident in het Microsoft 365-beveiligingscentrum":::

U kunt deze pagina ook zien door de naam van het gebruikersaccount te selecteren in de lijst op de **pagina** Gebruikers.

De gebruikerspagina van het Microsoft 365-beveiligingscentrum combineert gegevens van Microsoft Defender voor Eindpunt, Microsoft Defender voor identiteit en Microsoft Cloud App Security (afhankelijk van welke licenties u hebt). 

Op deze pagina ziet u informatie die specifiek is voor het beveiligingsrisico van een gebruikersaccount. Dit omvat een score die helpt bij het beoordelen van risico's en recente gebeurtenissen en waarschuwingen die hebben bijgedragen aan het algehele risico van de gebruiker.

Op deze pagina kunt u deze extra acties uitvoeren: 

- Het gebruikersaccount markeren als gecompromitteerd
- De gebruiker verplichten zich opnieuw aan te melden
- Het gebruikersaccount opschorten
- De gebruikersaccountinstellingen van Azure Active Directory (Azure AD) bekijken
- De bestanden weergeven die eigendom zijn van het gebruikersaccount
- Bestanden weergeven die met deze gebruiker zijn gedeeld. 

Hier is een voorbeeld.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Voorbeeld van de acties op een gebruikersaccount voor een incident in het Microsoft 365-beveiligingscentrum":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van incidenten](incidents-overview.md)
- [Prioriteit geven aan incidenten](incident-queue.md)
- [Incidenten beheren](manage-incidents.md)