---
title: Office 365 ATP Safe Links for Teams, safelinks, safe links, block malicious links, office 365 atp, Teams safe links, stop users from clicking bad links, malicious links
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Teams hebben nu toegang tot veilige links op het moment van uw klik. Of u nu chats 1-op-1 chats gebruikt, tussen Groepen of in Kanalen en Tabbladen, als u een abonnement hebt op Office 365 ATP, hebt u de mogelijkheid om deze veiligheidsfunctie in te schakelen en te gebruiken.
ms.openlocfilehash: 49a49bd41e71daf0afc9e7a24e79898ff98ad798
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212543"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a>Veilige koppelingen voor Office 365 in Teams

> [!IMPORTANT]
> Deze functie is vanaf 28 februari 2020 in **Public Preview** voor klanten in het Microsoft Teams Technology Adoption Program (TAP). Deze notitie wordt uit het artikel verwijderd wanneer Safe Links for Teams op grotere schaal beschikbaar is.

Microsoft Teams, een office 365 Cloud-toepassing voor het beheren van uw werk, maakt al gebruik van veilige bijlagen (voor Office 365), maar heeft nu toegang tot veilige koppelingen op het moment van uw klik. Of u nu chats 1-op-1 chats gebruikt, tussen groepen of in kanalen en tabbladen, als u een abonnement hebt op Office 365 ATP, u hebt de mogelijkheid om deze veiligheidsmaatregel in te schakelen en te gebruiken.

Zo werkt het: 

1. Wanneer u de Toepassing Teams start, controleert Office 365 of de gebruiker behoort tot een organisatie met Office 365 ATP en of de gebruiker deel uitmaakt van een actief beleid voor veilige koppelingen met de beveiliging ingeschakeld voor Microsoft Teams.

2. Als het bovenstaande waar is, worden URL's gevalideerd op het moment van klikken in Chats, Groepschats, Kanalen en in Tabbladen voor die gebruiker.

> [!NOTE]
> Veilige links beschermt gebruikers tegen links die worden verzonden door gastgebruikers, Federatieve gebruikers, tenantgebruikers. Als de aangemelde gebruiker veilige koppelingen voor Teams heeft ingeschakeld, zijn er veilige koppelingen van toepassing.
 
## <a name="what-will-users-experience"></a>Wat zullen gebruikers ervaren? 

Alle beschermde gebruikers hebben deze ervaring met gevaarlijke URL's: 

- Als op de koppeling is geklikt vanuit een Team-gesprek, groepschat of van kanalen, wordt een pagina weergegeven in de standaardbrowser. Als er op de koppeling is geklikt vanaf een vastgemaakt tabblad, wordt de pagina weergegeven in de GUI van Teams op dat tabblad en wordt de optie om in de browser te openen uitgeschakeld voor beveiligingsdoeleinden.

- Deze gebruiker wordt geblokkeerd om door te gaan naar de site van de URL.

Als de gebruiker die de koppeling heeft verzonden niet wordt beschermd door Office 365 ATP, kan hij of zij op de URL op zijn of haar machine klikken en de probleemsite oplossen. Dit maakt het dubbel belangrijk voor Office 365-beheerders om zich bewust te zijn van wie hun beschermde gebruikers zijn en moeten zijn.

![Een pagina Veilige koppelingen voor Teams die een kwaadaardige koppeling rapporteert en de doorvoer naar de pagina blokkeert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Als u op de knop *Teruggaan* op deze pagina in Teams klikt, wordt deze gesloten (of kan dit ertoe leiden dat gebruikers een lege pagina sluiten). Als u echter opnieuw op de link klikt, wordt de reputatie van de site opnieuw beoordeeld, zodat deze pagina opnieuw wordt weergegeven.

> [!NOTE]
>Sommige Office 365-beheerders schakelen het bericht **Doorgaan toch** in op de blokkeringspagina. Echter, als veilige links meet de reputatie van een site en vindt het ontbreekt, geen verdere click-through moet worden ondernomen. Het wordt niet aanbevolen dat gebruikers veiligheidsmaatregelen omzeilen. Gelieve dit af te wegen in uw overwegingen voordat u Toch doorgaan. 

