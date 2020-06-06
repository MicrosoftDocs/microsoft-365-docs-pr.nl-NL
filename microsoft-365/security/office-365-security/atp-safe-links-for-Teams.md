---
title: ATP Safe Links for Teams, safelinks, safe links, block malicious links, office 365 atp, Teams safe links, stop users from clicking bad links, malicious links ATP, ATP ATP, Teams safe links, stop users from clicking bad links, malicious links ATP, ATP
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
description: Teams hebben nu toegang tot veilige links op het moment van uw klik. Of u nu chats 1-op-1 chats gebruikt, tussen groepen of in kanalen en tabbladen, als u een abonnement hebt op Office 365 ATP, u deze veiligheidsfunctie inschakelen en gebruiken.
ms.openlocfilehash: d7586dba86c7ec9f43457b5510a1255e06bb6bf9
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588274"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Veilige links in teams

> [!IMPORTANT]
> Deze functie is vanaf 28 februari 2020 in **Public Preview** voor klanten in het Microsoft Teams Technology Adoption Program (TAP). Deze notitie wordt uit het artikel verwijderd wanneer Veilige links voor teams op grotere schaal beschikbaar zijn.

Microsoft Teams, een cloudtoepassing van Microsoft voor het beheren van uw werk, maakt al gebruik van veilige bijlagen (voor Office 365), maar heeft nu toegang tot Veilige koppelingen op het moment van uw klik. Of u nu Chats, Groepschats, kanalen of tabbladen gebruikt, als u een abonnement op Office 365 ATP hebt, u deze veiligheidsmaatregel inschakelen en gebruiken. Zie [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)voor meer informatie over licentievereisten.

Zo werkt het:

1. Wanneer u de Teams-toepassing start, controleert Microsoft 365 of de gebruiker deel uitmaakt van een organisatie met Office 365 ATP en of de gebruiker deel uitmaakt van een beleid voor actieve veilige koppelingen met de beveiliging ingeschakeld voor Microsoft Teams.

2. Als het bovenstaande waar is, worden URL's gevalideerd op het moment van klikken in Chats, Groepschats, Kanalen en in tabbladen voor die gebruiker.

## <a name="what-will-users-experience"></a>Wat zullen gebruikers ervaren?

Alle beschermde gebruikers hebben deze ervaring met gevaarlijke URL's:

- Als er op de koppeling is geklikt vanuit een teamgesprek, groepschat of kanalen, wordt een pagina weergegeven in de standaardbrowser. Als er op de koppeling is geklikt vanaf een vastgemaakt tabblad, wordt de pagina weergegeven in de GUI teams op dat tabblad en wordt de optie om in de browser te openen uitgeschakeld voor beveiligingsdoeleinden.

- Deze gebruiker wordt geblokkeerd om door te gaan naar de site van de URL.

Als de gebruiker die de koppeling heeft verzonden niet wordt beschermd door Office 365 ATP, is hij of zij vrij om op de URL op zijn of haar computer te klikken en de probleemsite op te lossen. Dit maakt het dubbel belangrijk voor beheerders om zich bewust te zijn van wie hun beschermde gebruikers zijn en moeten zijn.

![Een pagina Veilige links voor teams die een schadelijke koppeling rapporteert en de doorvoer naar de pagina blokkeert.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Als u op de knop *Teruggaan* op deze pagina in Teams klikt, wordt deze gesloten (of kan dit resulteren in een lege pagina die gebruikers kunnen sluiten). Het opnieuw klikken op de link zal echter resulteren in een herbeoordeling van de reputatie van de site, zodat deze pagina opnieuw verschijnt.

> [!NOTE]
> Sommige Microsoft 365-beheerders schakelen het bericht **Doorgaan hoe dan ook** in op de blokkeringspagina. Als Safe Links echter de reputatie van een site meet en deze niet merkt, moet er geen verdere doorklik worden ondernomen. Het wordt afgeraden dat gebruikers veiligheidsmaatregelen omzeilen. Weeg dit af in uw overwegingen voordat u Doorgaan inschakelt.
