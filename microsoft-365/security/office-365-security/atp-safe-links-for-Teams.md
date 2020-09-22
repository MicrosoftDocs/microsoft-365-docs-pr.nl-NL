---
title: Veilige verbindingen voor werknemers voor teams, safelinks, veilige koppelingen, schadelijke koppelingen blokkeren, Office 365 ATP, veilige koppelingen voor teams, stop gebruikers op beschadigde koppelingen, schadelijke koppelingen
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
description: Teams heeft nu toegang tot veilige koppelingen op het moment van de klikken. Als u een abonnement hebt op Office 365, kunt u gebruikmaken van deze veiligheidsfunctie, ongeacht of u chatsessies van 1 tot en met 1 gebruikt, tussen groepen of in kanalen en tabbladen.
ms.openlocfilehash: 362fb37b352a77aea07b899b707dbf4ac3d440d5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198749"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Veilige koppelingen in teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Deze functie is beschikbaar in de **openbare preview** voor klanten in het Microsoft teams-hulpprogramma voor Microsoft teams-technologie (tik) op 28 februari 2020. Deze opmerking wordt van het artikel verwijderd wanneer veilige koppelingen voor teams meer beschikbaar zijn.

Microsoft teams, een Microsoft-Cloud toepassing voor het beheren van uw werk, maakt al gebruik van veilige bijlagen (voor Office 365), maar deze functie heeft nu toegang tot veilige koppelingen op het moment van de klikken. Als u een abonnement hebt op Office 365 ATP, kunt u gebruikmaken van deze veiligheidsmaatregel, ongeacht of u chat gesprekken, groepsgesprekken, kanalen of tabbladen gebruikt. Zie voor meer informatie over licentievereisten [Microsoft 365 Licensing Services Licensing-instructies](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

Dit werkt als volgt:

1. Wanneer u de toepassing teams start, controleert Microsoft 365 of de gebruiker lid is van een organisatie met Office 365 ATP, en dat de gebruiker deel uitmaakt van een actief beleid voor veilige koppelingen met de bescherming ingeschakeld voor Microsoft teams.

2. Als de bovenstaande voorwaarden waar zijn, worden Url's gevalideerd wanneer u klikt op het moment van klikken in chats, groepsgesprekken, kanalen en de tabbladen van die gebruiker.

## <a name="what-will-users-experience"></a>Wat werken gebruikers?

Alle beveiligde gebruikers hebben deze ervaring met gevaarlijke Url's:

- Als u op de koppeling hebt geklikt vanuit een teams-gesprek, groepsgesprek of kanalen, wordt een pagina weergegeven in de standaardbrowser. Als u de koppeling hebt geklikt van het tabblad vastgemaakt, wordt de pagina weergegeven in de GEBRUIKERSINTERFACE van teams op dat tabblad en wordt de optie voor openen in browser uitgeschakeld vanwege beveiligingsredenen.

- Deze gebruiker wordt geblokkeerd en gaat verder met de site van de URL.

Als de gebruiker die de koppeling heeft verzonden, niet is beveiligd door Office 365 ATP, kan hij of zij op de URL van zijn of haar machine klikken en de probleem site oplossen. Dit maakt het twee belangrijke punten van de beheerder op de hoogte van de naam van de beveiligde gebruikers.

![Een pagina met veilige koppelingen voor teams die een kwaadaardige koppeling rapporteren en de transit voor de pagina blokkeren.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Als u op de knop *terug* op deze pagina in teams klikt, wordt deze gesloten, of kan een lege pagina worden gebruikt die gebruikers kunnen sluiten. Als u echter op de koppeling klikt, krijgt u een nieuwe beoordeling van de reputatie van de site zodat deze pagina opnieuw wordt weergegeven.

> [!NOTE]
> Sommige Microsoft 365-beheerders zullen het bericht **toch doorgaan** op de pagina met blokkeren activeren. Als u echter met veilige koppelingen de reputatie van een site aftreft en deze niet ziet, dan moet u verder klikken. Gebruikers wordt niet aangeraden veiligheidsmaatregelen over te slaan. Weeg dit in uw overwegingen voordat u toch doorgaan inschakelt.
