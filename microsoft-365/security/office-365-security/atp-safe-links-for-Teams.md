---
title: Office 365 ATP Safe Links for Teams, safelinks, safe links, block malicious links, office 365 atp, Teams safe links, stop gebruikers van het klikken op slechte links, kwaadaardige links
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
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
description: Teams hebben nu toegang tot veilige links op het moment van uw klik. Of u nu chats 1-op-1 Chats, tussen groepen of in kanalen en tabbladen gebruikt, als u een abonnement hebt op Office 365 ATP, u deze veiligheidsfunctie inschakelen en gebruiken.
ms.openlocfilehash: ba7ef2ae63b788ec94fbbb15c3c00312177a59d5
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "42809634"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a>Veilige koppelingen in Office 365 in teams

> [!IMPORTANT]
> Deze functie is vanaf 28 februari 2020 in **Openbare preview** voor klanten in het Microsoft Teams Technology Adoption Program (TAP). Deze notitie wordt uit het artikel verwijderd wanneer veilige koppelingen voor teams breder beschikbaar zijn.

Microsoft Teams, een office 365 Cloud-gebaseerde toepassing voor het beheren van uw werk, maakt al gebruik van veilige bijlagen (voor Office 365), maar heeft nu toegang tot veilige koppelingen op het moment van uw klik. Of u nu chats 1-op-1 Chats, tussen groepen of in kanalen en tabbladen gebruikt, als u een abonnement hebt op Office 365 ATP, u deze veiligheidsmaatregel inschakelen en gebruiken.

Zo werkt het: 

1. Wanneer u de toepassing Teams start, controleert Office 365 of de gebruiker deel uitmaakt van een organisatie die Office 365 ATP heeft en of de gebruiker deel uitmaakt van een actief beleid voor veilige koppelingen met de beveiliging die is ingeschakeld voor Microsoft Teams.

2. Als het bovenstaande waar is, worden URL's gevalideerd op het moment van klikken in Chats, Groepschats, Kanalen en in Tabbladen voor die gebruiker.
 
## <a name="what-will-users-experience"></a>Wat zullen gebruikers ervaren? 

Alle beschermde gebruikers hebben deze ervaring met gevaarlijke URL's: 

- Als er op de koppeling is geklikt vanuit een teamgesprek, groepschat of via kanalen, wordt een pagina weergegeven in de standaardbrowser. Als op de koppeling is geklikt vanaf een vastgemaakt tabblad, wordt de pagina weergegeven in de Gui Teams op dat tabblad en wordt de optie om in de browser te openen uitgeschakeld voor beveiligingsdoeleinden.

- Deze gebruiker wordt geblokkeerd om door te gaan naar de site van de URL.

Als de gebruiker die de koppeling heeft verzonden niet wordt beschermd door Office 365 ATP, is hij of zij vrij om op de URL op zijn of haar machine te klikken en de probleemsite op te lossen. Dit maakt het dubbel belangrijk voor Office 365-beheerders om zich bewust te zijn van wie hun beveiligde gebruikers zijn en moeten zijn.

![Een pagina Veilige koppelingen voor teams die een schadelijke koppeling rapporteert en de doorvoer naar de pagina blokkeert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Als u op de knop *Teruggaan* op deze pagina in Teams klikt, wordt deze gesloten (of kan dit resulteren in een lege pagina die gebruikers kunnen afsluiten). Als u echter opnieuw op de koppeling klikt, wordt de reputatie van de site opnieuw beoordeeld, zodat deze pagina opnieuw wordt weergegeven.

> [!NOTE]
>Sommige Office 365-beheerders schakelen het **bericht Doorgaan hoe dan ook** in op de blokkeringspagina. Echter, als veilige links maatregelen van de reputatie van een site en vindt het ontbreekt, geen verdere click-through moet worden ondernomen. Het wordt afgeraden dat gebruikers veiligheidsmaatregelen omzeilen. Weeg dit af in uw overwegingen voordat u Doorgaan toch inschakelt. 

